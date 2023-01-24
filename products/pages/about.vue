<template>
    <div>
        <h1>Product Listing App</h1>
        <p>App to display product listing</p>
    </div>
</template>

<script>
export default {
   head(){
        return {
            title: "Product listing in Nuxt",
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