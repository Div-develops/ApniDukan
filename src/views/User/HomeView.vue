<template>
    <main-header />

    <section class="hero__section" id="home">
        <div class="container">
            <div class="display-flex">
                <div class="hero__text">
                    <h4>Trade-in-offer</h4>
                    <h1>Super value deals</h1>
                    <h2>On all products</h2>
                    <p>Save more with coupons & get up to 70% off!</p>
                    <router-link to="/shop">
                        <action-button btnvalue="Start Shopping" />
                    </router-link>
                </div>
                <div>
                    <img src="@/assets/images/hero2.png" class="hero-img" />
                </div>
            </div>
        </div>
    </section>
    <service-section />

    <section id="about">
        <sub-header heading="#WhoWeAre" subHeading="Get to know us" />
        <div class="container">
            <article>
                <img src="@/assets/images/a6.webp" class="about-img" alt="Who we are" />
                <div class="about-text">
                    <h1>Who We Are ?</h1>
                    <p>
                        We pride ourselves to our delivery time and customer satisfaction
                        first approach. Our platform connects you to the best service
                        providers in your area. We are a team of young and passionate
                        individuals who are dedicated to providing you with the best service
                        possible.
                    </p>
                </div>
            </article>
        </div>
    </section>

    <section id="contact">
        <sub-header heading="#stayintouch" subHeading="With our 24/7 hotlines we will attend to you." />
        <div class="container">
            <div class="map-section">
                <div class="map-details">
                    <span>Get in touch</span>
                    <h3>Visit one of our agency locations or contact us today</h3>
                    <h4>Head Office</h4>
                    <ul>
                        <li>
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                class="bi bi-map" viewBox="0 0 16 16">
                                <path fill-rule="evenodd"
                                    d="M15.817.113A.5.5 0 0 1 16 .5v14a.5.5 0 0 1-.402.49l-5 1a.502.502 0 0 1-.196 0L5.5 15.01l-4.902.98A.5.5 0 0 1 0 15.5v-14a.5.5 0 0 1 .402-.49l5-1a.5.5 0 0 1 .196 0L10.5.99l4.902-.98a.5.5 0 0 1 .415.103zM10 1.91l-4-.8v12.98l4 .8V1.91zm1 12.98 4-.8V1.11l-4 .8v12.98zm-6-.8V1.11l-4 .8v12.98l4-.8z" />
                            </svg>
                            <p>56 Glassfor Street Glasgow G1 1UL New York</p>
                        </li>
                        <li>
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                class="bi bi-envelope" viewBox="0 0 16 16">
                                <path
                                    d="M0 4a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V4Zm2-1a1 1 0 0 0-1 1v.217l7 4.2 7-4.2V4a1 1 0 0 0-1-1H2Zm13 2.383-4.708 2.825L15 11.105V5.383Zm-.034 6.876-5.64-3.471L8 9.583l-1.326-.795-5.64 3.47A1 1 0 0 0 2 13h12a1 1 0 0 0 .966-.741ZM1 11.105l4.708-2.897L1 5.383v5.722Z" />
                            </svg>
                            <p>apnidukan@gmail.co.uk</p>
                        </li>
                        <li>
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                class="bi bi-telephone-fill" viewBox="0 0 16 16">
                                <path fill-rule="evenodd"
                                    d="M1.885.511a1.745 1.745 0 0 1 2.61.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.678.678 0 0 0 .178.643l2.457 2.457a.678.678 0 0 0 .644.178l2.189-.547a1.745 1.745 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.634 18.634 0 0 1-7.01-4.42 18.634 18.634 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877L1.885.511z" />
                            </svg>
                            <p>+01-2222-365/+01-2343-563</p>
                        </li>
                        <li>
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                class="bi bi-clock" viewBox="0 0 16 16">
                                <path
                                    d="M8 3.5a.5.5 0 0 0-1 0V9a.5.5 0 0 0 .252.434l3.5 2a.5.5 0 0 0 .496-.868L8 8.71V3.5z" />
                                <path d="M8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm7-8A7 7 0 1 1 1 8a7 7 0 0 1 14 0z" />
                            </svg>
                            <p>Monday to Saturday: 8:00am to 8:00pm</p>
                        </li>
                    </ul>
                </div>
            </div>

            <div class="form-section">
                <form>
                    <span>Leave a message</span>
                    <h3>We love to hear from you</h3>

                    <div class="form-control">
                        <input type="text" placeholder="Your name" required />
                    </div>
                    <div class="form-control">
                        <input type="email" placeholder="E-mail" required />
                    </div>
                    <div class="form-control">
                        <input type="text" placeholder="Subject" required />
                    </div>
                    <div class="form-control">
                        <textarea id="" cols="30" rows="10" placeholder="Your Message"></textarea>
                    </div>
                    <action-button btnvalue="Submit" />
                </form>
            </div>
        </div>
    </section>
</template>

<script>
import ActionButton from "@/components/ActionButton.vue";
import SubHeader from "@/components/SubHeader.vue";
import MainHeader from "@/components/MainHeader.vue";


export default {
    name: "HomeView",
    components: {
        MainHeader,
        SubHeader,
    },

};
</script>

<style scoped>
/* Hero Section */

.display-flex {
    display: flex;
}

.hero__section {
    display: flex;
    align-items: center;
    justify-content: center;
    height: calc(100vh - 65px);
    background-color: beige;
    background-position: -70% 50%;
    background-size: cover;
}

.hero__text {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
}

.hero-img {
    margin-top: 5rem;
}

.hero__text h4 {
    padding-bottom: 1rem;
}

.hero__text h1 {
    color: var(--dim-blue);
}

.hero__text p {
    margin-bottom: 1rem;
}

@media (min-width: 2000px) {
    .hero__section {
        background-position: 70% 12%;
        background-size: contain;
        background-repeat: no-repeat;
        background-color: #e3e6f3;
        height: 50vh;
    }
}

/*About section */
article {
    display: flex;
    gap: 4rem;
    margin-bottom: 2.5rem;
}

.about-img {
    width: 50%;
    object-fit: cover;
}

.about-text {
    width: 50%;
}

.about-text p {
    line-height: 25px;
}

@media (max-width: 499px) {

    .display-flex {
        display: flex;
        flex-direction: column-reverse;
    }

    .hero-img{
        margin-right: 16rem;
        width:99%;
    }

    article {
        flex-direction: column;
    }

    .about-img,
    .about-text,
    .video-banner {
        width: 100%;
    }

    h1 {
        font-size: 4rem;
    }
}

/*Contact section */

span {
    text-transform: uppercase;
    font-size: 1.5rem;
}

li {
    display: flex;
    align-items: center;
    gap: 2rem;
}

/* Form */

.form-section {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    padding-block: 5rem;
    gap: 3rem;
}

form {
    width: 70%;
}

form h3 {
    padding-block: 2rem;
}

.form-control {
    padding-bottom: 2rem;
}

input,
textarea {
    width: 100%;
    border: 1px solid lightgrey;
}

input:hover,
textarea:hover {
    outline: none;
    border: 1px solid black;
}

@media (max-width: 799px) {
    form {
        width: 50%;
    }
}

@media (max-width: 599px) {
    .map-section {
        flex-direction: column;
    }

    .map-details,
    .map,
    form {
        width: 100%;
    }

    form h3 {
        font-size: 2.7rem;
    }

    .form-section {
        flex-direction: column;
        gap: 3rem;
    }
}

@media (min-width: 3000px) {
    .hero__section {
        background-position: 60% 30%;
        /* background-size: cover; */
    }
}
</style>
