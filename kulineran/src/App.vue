<template>
    <div id="app">
        <router-view></router-view>
        <Footer/>
    </div>
</template>
<script>
import Footer from '@/components/Footer.vue'
export default {
    component: {
        Footer
    }
}
</script>
<style>
</style>