<template>
<nuxt-link :to="'/products/' + id ">
    <div class="product">
        <p>{{ product }} <img :src="image" width="100" height="100"/></p>
    </div>
</nuxt-link> 

</template>
<script>
export default {
    name: "Product",
    props: ["product", "image", "id"]
}
</script>

<style>
.product { padding: 1rem; border: 1px dotted #ccc; margin: 1rem 0;}
</style>