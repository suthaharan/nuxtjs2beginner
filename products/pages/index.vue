<template>
  <div>
    <h2>Welcome to our Sample Products App!!</h2>
  </div>
</template>

<script>
export default {
  layout: 'default',
   head(){
        return {
            title: "Welcome to Sample Product listing in Nuxt",
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
