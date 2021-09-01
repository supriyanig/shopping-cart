<template>
    <div class="cart-item-card">
        <h3>Crt Total: ${{cart_total.toFixed(2)}}</h3>
        <button class="view-product-button">Pay By credit Card</button>
    </div>
</template>
<script>
export default {
    components:{

    },
    // props:['products'],
    computed:{
        cart_total(){
            return this.$store.getters.cartTotal
        }
    }
}
</script>