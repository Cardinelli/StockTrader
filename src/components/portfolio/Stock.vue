<template>
    <div class="col-sm-6 col-md-4">
        <div class="panel panel-primary">
            <div class="panel-heading">
                <h3 class="panel-title">
                    {{stock.name}}
                    <small> (price: {{stock.price}} || Quantity: {{stock.quantity}}) </small>
                </h3>
            </div>
            <div class="panel-body ">
                <div class="pull-left">
                    <input
                            type="number"
                            class="form-control"
                            placeholder="Quantity"
                            :class="{danger: insufficientQuantity}"
                            v-model="quantity">
                </div>
                <div class="pull-right">
                    <button class="btn btn-success"
                            @click="sellStock"
                            :class="{warning: insufficientQuantity}"
                            :disabled="quantity <= 0 || insufficientQuantity ">Sell
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import {mapActions} from 'vuex';

    export default {
        props: ['stock'],
        data() {
            return {
                quantity: 0
            }
        },
        computed: {
            insufficientQuantity() {
                return this.quantity > this.stock.quantity;
            },
        },
        methods: {
            ...mapActions({
                placeSellOrder: 'sellStock'
            }),
            sellStock() {
                const order = {
                    stockId: this.stock.id,
                    stockPrice: this.stock.price,
                    quantity: this.quantity,
                };
                this.placeSellOrder(order);
                this.quantity = 0;
            }
        }
    }


</script>

<style scoped>
    .danger {
        border: 1px solid crimson;
    }
    .warning {
        background-color: crimson;
    }

</style>