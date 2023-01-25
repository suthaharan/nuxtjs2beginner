<template>
<div>
    <SearchProducts v-on:search-text="searchText"/>
    <Product v-for="product in products" :key="product.id" :id="product.id" :brand="product.brand" :category="product.category"  :title="product.title" :image="product.images[0]"/>
</div>
</template>

<script>
import axios from "axios";
import Product from "../../components/Product";
import SearchProducts from "../../components/SearchProducts";

export default {
   layout: 'default',
   components: {
    Product,
    SearchProducts
   },
   data(){
    return {
        products: []
    }
   },
   async created(){
    const config = {
        headers: {
            'Accept': 'application/json'
        }
    }

    try{
        const res = await axios.get("https://dummyjson.com/products", config);
         console.log("in created ...");
        console.log(res.data);
        this.products = res.data.products;
    }catch (err){
        console.log(err);
    }
   },
   methods:{
    async searchText(text){
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try{
            const res = await axios.get(`https://dummyjson.com/products/search?q=${text}`, config);
            console.log("in methods ...");
            this.products = res.data.products;
        }catch (err){
            console.log(err);
        }
    }
   },
   head(){
        return {
            title: "Main Sample Product listing in Nuxt",
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

</style>