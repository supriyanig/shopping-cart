<template>
  <div class="home">
    <ProductDescriptionDrawer :product="product" :active="active.product_drawer" v-on:close-product-drawer="closeProductDrawer()"/>
    <div class="product-cart-container">
      <ProductSummaryCart v-for="product in items" :key="product.id" 
      v-on:view-product="viewProduct($event)"
      :product="product" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import items from '../data/items.js';
import ProductSummaryCart from '../components/products/ProductSummaryCart';
import ProductDescriptionDrawer from '../components/products/ProductDescriptionDrawer';
export default {
  name: 'Home',
  components: {
    ProductSummaryCart,
    ProductDescriptionDrawer
  },
  data(){
    return{
      items:items,
      product:null,
      active:{
        product_drawer:false
      }
    }
  },
  methods:{
    viewProduct(product){
      this.product=product;
      this.active.product_drawer=true;
      console.log(this.product);
    },
    closeProductDrawer(){
      this.active.product_drawer=false;
    }
  }
}
</script>
<style lang="scss">
.product-cart-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
