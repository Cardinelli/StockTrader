<template>
    <nav class="navbar navbar-light bg-light">
        <div class="navbar-header">
            <router-link class="navbar-brand" to="/">
                Stock Trader
            </router-link>
        </div>
        <form class="form-inline">
            <router-link class="alink" to="/portfolio"
                         active-class="active"><a class="btn  btn-outline-info" > Portfolio </a></router-link>
            <router-link class="alink" to="/stocks"
                         active-class="active"><a class="btn  btn-outline-info"> Stocks </a></router-link>
            <router-link class="alink" to="/"
                         active-class="active"><a class="btn  btn-outline-info"> End Day </a></router-link>

            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                Save / Load
            </a>
            <div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
                <a class="dropdown-item" href="#">Save Data</a>
                <a class="dropdown-item" href="#">Load Data</a>
            </div>
        </form>
    </nav>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped>

    .alink {
        border:none;
        margin: 2px;
        text-decoration: none;
        color: #1b2735;
    }

    .alink:hover {
        transition: 0.5s;
        background-color: deepskyblue;
        border-radius: 50px;
        color: white;
    }

</style>