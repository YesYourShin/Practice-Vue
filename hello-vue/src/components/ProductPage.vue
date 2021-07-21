<template>
    <div id="app">
        <div class='nav-bar'></div>
        <div class="cart">
            <p>Cart{{ cart.length }}</p>
        </div>
        <Product @add-to-cart="addToCart"></Product>
        <Product @add-to-cart="addToCart"></Product>
        <Comment></Comment>
    </div>    
</template>

<script>
import Product from './Product.vue'
import Comment from './Comment.vue'

export default{
    name:'ProductPage',
    components:{
        Product,
        Comment
    },
    data(){
        return {cart:[]}
    },
    methods:{
        addToCart(variantId){
            this.cart.push(variantId)
        }
    }
}
</script>
