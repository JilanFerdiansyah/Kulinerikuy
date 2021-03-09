<template>
    <div class="FoodDetail">
        <Navbar></Navbar>
        <div class="container">
            <!--breadcumb-->
            <div class="row mt-5">
                <div class="col">
                    <nav aria-label="breadcrumb">
                        <ol class="breadcrumb">
                            <li class="breadcrumb-item">
                                <router-link class="text-dark" to="/">Home </router-link>
                            </li>
                            <li class="breadcrumb-item">
                                <router-link class="text-dark" to="/foods">Food </router-link>
                            </li>
                            <li class="breadcrumb-item active" aria-current="page">Food Order</li>
                        </ol>
                    </nav>
                </div>
            </div>
            <div class="row mt-3">
                <div class="col-md-6">
                    <img :src="'../assets/img/' + product.gambar" class="img-fluid shadow" alt="">
                </div>
                <div class="col-md-6">
                    <h2><strong>{{product.nama}}</strong></h2>
                    <hr>
                    <h4>Harga : <strong>{{product.harga}}</strong></h4>
                    <form class="mt-4" v-on:submit.prevent>
                        <div class="form-group">
                            <label for="jumlah_pemesanan">Jumlah Pesan</label>
                            <input type="number" class="form-control" v-model="pesan.jumlah_pemesanan" />
                        </div>
                        <div class="form-group">
                            <label for="keterangan">Keterangan</label>
                            <textarea v-model="pesan.keterangan" class="form-control" placeholder="Keterangan spt : Pedes, Nasi Setengah .."></textarea>
                        </div>
                        <button type="submit" class="btn btn-success" @click="pemesanan">
                            <b-icon-cart></b-icon-cart>Pesan
                        </button>
                    </form>
                </div>
            </div>
        </div>
        <Footer></Footer>
    </div>
</template>
<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

import axios from 'axios';
export default {
    name: 'FoodDetail',
    components: {
        Navbar,
        Footer
    },
    data() {
        return {
            product: {},
            pesan: {},
        }
    },
    methods: {
        setProduct(data) {
            this.product = data;
        },
        pemesanan() {
            if (this.pesan.jumlah_pemesanan) {
                this.pesan.products = this.product;
                axios
                    .post("http://localhost:3000/keranjangs", this.pesan)
                    .then(() => {
                        this.$router.push({ path: "/keranjang"})
                        this.$toast.success('Sukses masuk keranjang.', {
                            type: 'success',
                            position: 'top-right',
                            duration: 3000,
                            dismissable: true
                        })
                    })
                    .catch((err) => console.log(err))
            } else {
                this.$toast.error('Jumlah Pesanan Harus Di Isi', {
                    type: 'error',
                    position: 'top-right',
                    duration: 3000,
                    dismissable: true
                })
            }

        }
    },
    mounted() {
        axios.get("http://localhost:3000/products/" + this.$route.params.id)
            .then((response) => this.setProduct(response.data))
            .catch((error) => console.log("Gagal : ", error))
    }
};
</script>