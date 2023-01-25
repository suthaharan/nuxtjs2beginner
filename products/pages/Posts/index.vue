<template>
<div class="container">
    <h4>Posts you might enjoy</h4>
    <nuxt-link v-for="post in posts"
    :to="{name: 'Posts-id', params: {id: post.id}}"
    :key="post.id" class="button--grey">{{post.title}}</nuxt-link>
</div>
</template>

<script>

export default {
   
   computed:{
    posts(){
        // using vuex store
        return this.$store.state.posts.all;
        }
   } 
}
</script>

<style>
.displaypost{text-align: center;}
.button--grey{display: inline-block;}
</style>