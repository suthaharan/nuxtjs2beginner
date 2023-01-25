<template>
<div>
    <nuxt-link to="/products">Back to Products</nuxt-link>
    <div class="displayproduct">
    <h2> {{ product.title }} : {{ product.brand }} </h2>
    <img :src="product.thumbnail" width="100" height="100"/>
    </div>
    <p>{{ product.description }}</p>
    <hr />
    <small>Product ID: {{ $route.params.id }}</small>
</div>
</template>

<script>
import axios from "axios";
export default {
   layout: 'default',
   data(){
    return {
        product: {}
    }
   },
   async created(){
    const config = {
        headers: {
            'Accept': 'application/json'
        }
    }
    try{
        const res = await axios.get(`https://dummyjson.com/products/${this.$route.params.id}`, config);
        console.log(res.data);
        this.product = res.data;
    }catch (err){
        console.log(err);
    }
   },
   head(){
        return {
            title: this.product.brand,
            meta: [
                {
                    hid: "description",
                    name: "description about the proudcts app",
                    content: "best place to list your products"
                }
            ]
        }
    } 
}
</script>

<style>
.displayproduct{text-align: center;}
</style>