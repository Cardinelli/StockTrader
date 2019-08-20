<template>
    <div>
       <app-stocks v-for="stock in stocks" :stock="stock"></app-stocks>
    </div>
</template>

<script>
    import {mapGetters} from 'vuex';
    import Stock from "../../components/portfolio/Stock.vue";
    export default {
       computed: {
           ...mapGetters({
              stocks: 'stockPortfolio'
           })
       },
        components: {
           appStock: Stock
        }
    }


</script>

<style scoped>

</style>