<template>
  <main-header />
  <section class="container">
    <router-link to="/shop" id="back"
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
        class="bi bi-arrow-left"
        viewBox="0 0 16 16"
      >
        <path
          fill-rule="evenodd"
          d="M15 8a.5.5 0 0 0-.5-.5H2.707l3.147-3.146a.5.5 0 1 0-.708-.708l-4 4a.5.5 0 0 0 0 .708l4 4a.5.5 0 0 0 .708-.708L2.707 8.5H14.5A.5.5 0 0 0 15 8z"
        /></svg
    ></router-link>
    <div class="cart-item" v-if="loaded">
      <div class="image-section">
        <img :src="activeImage" class="main-img" />
        <div class="img-thumbnails">
          <template v-if="product.images">
            <img
              v-for="(image, index) in product.images.slice(0, 4)"
              :key="index"
              :src="image"
              class="thumbnail"
              @click="setActiveImage(index)"
            />
          </template>
        </div>
      </div>
      <div class="product-details">
        <span>Home / {{ product.category }}</span>
        <h4>{{ product.title }}</h4>
        <h4>{{ formattedPrice }}</h4>
        <select v-model="size">
          <option disabled>Select Size</option>
          <option>Medium</option>
          <option>XL</option>
          <option>XXL</option>
          <option>Small</option>
        </select>
        <p class="weak" v-if="validSize">Please select a size</p>
        <div class="add-to-cart">
          <action-button btnvalue="Add To Cart" @click="addItemToCart" />
        </div>
        <h4>Product Details</h4>
        <p class="product-description">
          {{ product.description }}
        </p>

        <div class="checkout">
        <h3>Order Details</h3>
        <table>
            <thead>
                <tr>
                    <td>Item Price</td>
                    <td>Rs {{ product.price.toFixed(2) }}</td>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>GST (18%)</td>
                    <td>Rs {{ gst.toFixed(2) }}</td>
                </tr>
                <tr>
                    <td><strong>Total</strong></td>
                    <td>
                        <strong>Rs {{ total.toFixed(2) }}</strong>
                    </td>
                </tr>
            </tbody>
        </table>
        </div>
      </div>
    </div>

    <product-preloader v-else> Loading Product... </product-preloader>
  </section>
</template>

<script>
import ProductCard from "@/components/home_components/cards/ProductCard.vue";
import ActionButton from "@/components/ActionButton.vue";
import MainHeader from "@/components/MainHeader.vue";
import ProductPreloader from "@/components/preloaders/ProductPreloader.vue";

import axios from "axios";

export default {
  name: "CartItemView",
  components: {
    ProductCard,
    ActionButton,
    MainHeader,
    ProductPreloader,
  },
  data() {
    return {
      activeImage: "",
      product: {price: 0,},
      loaded: false,
      size: "Select Size",
        quantity: 1,
        gst: 0, 
        total: 0, 
      validSize: false,
    };
  },
  methods: {
    setActiveImage(image) {
      this.activeImage = this.product.images[image];
    },
  },
  computed: {
    formattedPrice() {
      return "Rs " + this.product.price.toFixed(2);
    },
  },
  async created() {
    let productId = this.$route.params.id;
    let res = await axios.get(`https://fakestoreapi.com/products/${productId}`);
    this.product = res.data;
    this.loaded = true;
      this.activeImage = this.product.image;
      this.gst = this.product.price * 0.18;
      this.total = this.product.price * this.quantity+ this.gst;
  },
};
</script>

<style scoped>
.cart-item {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 5rem;
  padding-bottom: 2rem;
  margin-top: 10px;
}

.image-section {
  width: 47%;
}

.image-section,
.product-details {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

#back {
  padding: 1rem 1.8rem;
  font-size: 2rem;
  border: none;
  border-radius: 6px;
  color: white;
  font-weight: 600;
  background-color: var(--dark-blue);
  transition: opacity 0.25s;
  display: grid;
  place-content: center;
  width: fit-content;
}

#back:hover {
  opacity: 0.85;
}

.main-img {
  height: 55vh;
  max-width: 100%;
  object-fit: contain;
}

.img-thumbnails {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0.5rem;
  padding-top: 1rem;
  width: 100%;
}

.img-thumbnails .thumbnail {
  height: auto;
  max-width: 100%;
  cursor: pointer;
}

.img-thumbnails .thumbnail:hover {
  opacity: 0.7;
}

/* Product Details */
.product-details {
  width: 60%;
  padding-block: 2.5rem;
}

.product-details span {
  font-size: 1.4rem;
}

.product-details h4 {
  padding: 1.5rem 0 1rem 0;
}

.product-details select {
  max-width: 120px;
  padding: 0.8rem 1rem;
  margin-bottom: 2rem;
  font-size: 1.5rem;
  cursor: pointer;
}

.extra {
  padding-block: 4.5rem;
  text-align: center;
}

.product-description {
  line-height: 2.5rem;
}


/* Checkout */
.checkout {
    width: 60%;
}

.checkout table {
    margin-bottom: 2rem;
    font-size: 20px;
    
}

.checkout td {
    border: 1px solid lightgrey;
    padding-inline: 4rem;
    padding-block: 1rem;
}

@media (max-width: 599px) {
  .cart-item {
    flex-direction: column;
  }
  .image-section,
  .product-details {
    width: 100%;
  }

  .image-section {
    padding-top: 2rem;
  }
  .image-section a {
    top: -2rem;
    left: 0;
  }
}
</style>
