<template>
    <div class="card shadow card-product">
        <img :src="'/assets/img/' + product.gambar" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ product.nama }}</h5>
            <p class="card-text">Harga : Rp. {{product.harga}}</p>
            <router-link href="#" class="btn btn-success" :to="'/foods/'+product.id"><b-icon-cart class="mr-2"></b-icon-cart>Pesan</router-link>
        </div>
    </div>
</template>
<script>
export default {
    name: 'CardProduct',
    props: ['product']
}
</script>