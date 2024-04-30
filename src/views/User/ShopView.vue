<template>
    <main-header />
    <sub-header
        heading="#stayhome"
        subHeading="Save more with coupons up to 70% off"
    />
    <div class="container">
        <div class="product__container" v-if="loaded">
            <product-card
                v-for="(product, index) in products"
                :key="index"
                :productId="product.id"
                :productName="product.title"
                :brand="product.category"
                :price="product.price"
                :currency="'Rs'" 
                :ratings="product.rating.rate"
                :image_url="product.image"
                :in_stock="true" 
            />
        </div>
        <product-preloader v-else> Loading products... </product-preloader>
    </div>

    <main-footer />
</template>

<script>
import SubHeader from "@/components/SubHeader.vue";
import ProductCard from "@/components/home_components/cards/ProductCard.vue";
import ProductPreloader from "@/components/preloaders/ProductPreloader.vue";

import MainHeader from "@/components/MainHeader.vue";

import axios from "axios";

export default {
    name: "ShopView",
    components: {
        SubHeader,
        ProductCard,
        MainHeader,
        "product-preloader": ProductPreloader,
    },
    data() {
        return {
            products: [],
            loaded: false,
        };
    },
    created() {
        this.getProducts();
    },
    methods: {
        getProducts() {
            this.loaded = false;
            axios
                .get("https://fakestoreapi.com/products")
                .then((res) => {
                    this.products = res.data;
                    this.loaded = true;
                })
                .catch((err) => {
                    console.log(err);
                    this.loaded = false;
                });
        },
    },
};
</script>

<style>
.product__container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
    padding-block: 4rem;
}
</style>
