<template>
<nuxt-link :to="'/products/' + id ">
    <div class="product">
        <p>Brand: {{ brand }}</p>
        <p>Title: {{ title }}</p>
        <p>Category: {{ category }}</p>
    </div>
</nuxt-link> 

</template>
<script>
export default {
    name: "Product",
    props: ["brand", "title", "category", "image", "id"]
}
</script>

<style>
.product { padding: 1rem; border: 1px dotted #ccc; margin: 1rem 0;}
</style>