<template>
<div class="container">
    <nuxt-link to="/">Back to Home</nuxt-link>
    <div class="displaypost">
        <h1 class="title">{{ post.title}}</h1>
    </div>
    <p>{{ post.body }}</p>
    <hr />
    <small>Post ID: {{ $route.params.id }}</small>
    <br/>
    <div class="relatedposts">
        <h4>Posts you might enjoy</h4>
        <ul>
            <li v-for="related in relatedPosts" :key="related.id">
                &raquo; <nuxt-link :to="`/posts/${related.id}`">{{related.title}}</nuxt-link>
            </li>
        </ul>
    </div>
</div>
</template>

<script>

export default {
   data(){
    return {
        id: this.$route.params.id,
        posts: [
                    {
                        "userId": 1,
                        "id": 1,
                        "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                        "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
                    },
                    {
                        "userId": 1,
                        "id": 2,
                        "title": "qui est esse",
                        "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
                    },
                    {
                        "userId": 1,
                        "id": 3,
                        "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
                        "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
                    },
                    {
                        "userId": 1,
                        "id": 4,
                        "title": "eum et est occaecati",
                        "body": "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit"
                    },
                    {
                        "userId": 1,
                        "id": 5,
                        "title": "nesciunt quas odio",
                        "body": "repudiandae veniam quaerat sunt sed\nalias aut fugiat sit autem sed est\nvoluptatem omnis possimus esse voluptatibus quis\nest aut tenetur dolor neque"
                    }
                ]
    }
   },
   computed:{
    post(){
        console.log("passed id " + this.id);
        console.log(this.posts);
        return this.posts.find(post => post.id == this.id);
        },
    relatedPosts() {
        return this.posts.filter(post => post.id !== this.id)
    }
   },
   head(){
        return {
            title: this.post.title,
            meta: [
                {name: 'twitter:title', content: this.post.title},
                {name: 'twitter:description', content: this.post.body},
                {name: 'twitter:image', content: ''},
                {name: 'twitter:card', content: 'summary_large_image'},
            ]
        }
    } 
}
</script>

<style>
.displaypost{text-align: center;}
</style>