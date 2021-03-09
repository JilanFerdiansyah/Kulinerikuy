<template>
    <div class="main">
        <div class="desktop d-none d-md-block">
            <div class="row mt-4 hero">
                <div class="col md-6">
                    <div class="d-flex h-100">
                        <div class="justify-content-center align-self-center">
                            <h2><strong>Delicious food menu,</strong> <br>in your gadget</h2>
                            <p>Ayo segera pilih makanan anda</p>
                            <router-link class="btn btn-lg btn-success" to="/Foods">
                                <b-icon-arrow-right></b-icon-arrow-right>Pesan
                            </router-link>
                        </div>
                    </div>
                </div>
                <div class="col md-6">
                    <img src="../assets/img/hero6.png" style="margin:auto;" alt="">
                </div>
            </div>
        </div>
        <div class="mobile d-sm-block d-md-none">
            <div class="row mt-4 hero">
                <div class="col md-6">
                    <img src="../assets/img hero6.png" style="margin:auto;" alt="">
                </div>
                <div class=" col md-6">
                    <div class="d-flex h-100">
                        <div class="justify-content-center align-self-center">
                            <h2><strong>Delicious food menu,</strong> <br>in your gadget</h2>
                            <p>Ayo segera pilih makanan anda</p>
                            <router-link class="btn btn-lg btn-success" to="/Foods">
                                <b-icon-arrow-right></b-icon-arrow-right>Pesan
                            </router-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Hero',

}
</script>
<style>
</style>