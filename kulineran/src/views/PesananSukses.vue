<template>
    <div class="pesanan-sukses">
        <Navbar></Navbar>
        <div class="container">
            <div class="row justify-content-center mt-5">
                <div class="col text-center">
                    <img src="../assets/img/hero6.png" style="margin:auto;" alt="">
                    <h2><strong>SUKSES</strong></h2>
                    <h4>pesanan anda segera di proses <br>Selamat menunggu</h4>
                </div>
            </div>
        </div>
        <Footer></Footer>
    </div>
</template>
<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

export default {
    name: 'PesananSukses',
    components: {
        Navbar,
        Footer
    },
}
</script>