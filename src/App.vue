<template>
    <div class="container">
        <br>
        <app-header/>
        <br>
        <div class="row">
            <div class="col-xs-12">
                <router-view/>
            </div>
        </div>
    </div>
</template>

<script>
    import Header from "./components/Header.vue";

    export default {
        components: {
            appHeader: Header,
        }
    }
</script>

<style>

    body {
        /*padding: 30px;*/
        color:white;
        /*display: flex;*/
        /*margin: auto;*/
        /*width: 100vh;*/
        /*height: 100vh;*/
        background-color: #1b2735;
    }

</style>
