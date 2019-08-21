<template>
   <div>
       <br>
       <div class="panel panel-primary">
           <div class="panel-heading">Trade or View your Portfolio</div>
           <div class="panel-body">You may Save & Load your Data</div>
           <div class="panel-body">Click on 'End Day' to begin a New Day</div>
           <div class="panel-heading"> Your Funds: {{ funds }} <span> <i class="fas dollar fa-dollar-sign"></i> </span> </div>
       </div>

   </div>
</template>

<script>
    export default {
        computed: {
            funds() {
                return this.$store.getters.funds;
            },
        }
    }
</script>

<style scoped>

    .panel-body {
        color:#1b2735;
    }
    .dollar {
        color: #1b2735;
    }

</style>