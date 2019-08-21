<template>
    <nav class="navbar navbar-default">
        <div class="container-fluid">
            <div class="navbar-header">
                <router-link to="/" class="navbar-brand"> Stock Trader</router-link>
            </div>
            <ul class="nav navbar-nav">
                <router-link to="/portfolio" active-class="active" tag="li"><a> Portfolio </a></router-link>
                <router-link to="/stocks" active-class="active" tag="li"><a> Stocks </a></router-link>
            </ul>
            <strong class="navbar-text"> Funds: {{ funds }} <span> <i class="fas  fa-dollar-sign"></i></span> </strong>
            <ul class="nav navbar-nav navbar-right">
                <li><a href="#" @click="endDay"> End Day </a></li>
                <li class="dropdown"
                    :class="{open: isDropdownOpen}"
                    @click="isDropdownOpen = !isDropdownOpen"
                >
                    <a class="dropdown-toggle" data-toggle="dropdown" href="#">Save / Load
                        <span class="caret"></span></a>
                    <ul class="dropdown-menu">
                        <li><a href="#">Save</a></li>
                        <li><a href="#">Load</a></li>
                    </ul>
                </li>
            </ul>

        </div>
    </nav>
</template>

<script>
    import {mapActions} from 'vuex';


    export default {
        data() {
            return {
                isDropdownOpen: false
            }
        },
        computed: {
            funds() {
                return this.$store.getters.funds;
            }
        },
        methods: {
            ...mapActions([
                'randomizeStocks'
            ]),
            endDay() {
                this.randomizeStocks();
            }
        }
    }
</script>

<style scoped>

    .dollar {
        color: #1b2735;
    }

</style>