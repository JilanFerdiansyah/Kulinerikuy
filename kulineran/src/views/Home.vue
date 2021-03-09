<template>
    <div class="home">
        <Navbar />
        <div class="container">
            <Hero/>
            <div class="row mt-4">
                <div class="col">
                    <h2>Best <strong>foods</strong></h2>
                </div>
                <div class="col">
                    <router-link to="/Foods" class="btn btn-success float-right">
                        <b-icon-eye class="mr-2"></b-icon-eye>Lihat Semua
                    </router-link>
                </div>
            </div>
            <div class="row mt-3">
                <div class="col-md-4" v-for="product in products" :key="product.id">
                    <CardProduct :product="product"></CardProduct>
                </div>
            </div>
        </div>
        <Footer></Footer>
    </div>
</template>
<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue';
import Hero from '@/components/Hero.vue';
import CardProduct from '@/components/CardProduct.vue';
import Footer from '@/components/Footer.vue';


import axios from 'axios';

export default {
    name: 'Home',
    components: {
        Navbar,
        Hero,
        Footer,
        CardProduct,
        
  

    },
    data() {
        return {
            products: []
        }
    },
    methods: {
        setProducts(data) {
            this.products = data
        }
    },
    mounted() {
        axios.get("http://localhost:3000/best-products")
            .then((response) => this.setProducts(response.data))
            .catch((error) => console.log("Gagal : ", error))
    }
}
</script>