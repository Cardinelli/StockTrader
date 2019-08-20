<template>
    <div>
        <app-stock v-for="stock in stocks"> </app-stock>

    </div>
</template>

<script>
    import Stock from "./Stock.vue";
    export default {
        data() {
            return {
                stocks: [
                    {id: 1, name: 'BmW', price: 100},
                    {id: 2, name: 'Apple', price: 200},
                    {id: 3, name: 'Opel', price: 300},
                    {id: 4, name: 'Twitter', price: 500},
                ]
            }
        },
        components: {
            appStock: Stock,
        }
    }
</script>

<style scoped>

</style>