# NuxtJS 2 Beginner

* API's used: https://dummyjson.com/docs/products
* References
  * Nuxt2 Get Started: https://nuxtjs.org/docs/get-started/installation
  * Nuxt2 Examples: https://nuxtjs.org/examples/routing/hello-world
  * Vue.js nation: https://vueschool.io/courses/nuxtjs-fundamentals
  * YouTube Traversy: https://www.youtube.com/watch?v=ltzlhAxJr74&t=477s


### NuxtJS

* Framework that offers server side rendering for Vue applications

* Advantages
  * Universal apps for server side rendering
  * Help in SEO (preloads app to help in SEO)
  * Vue meta is manage header tags
  * Easy to use Routing mechanism
  * We can use universal vs. SPA when we build apps
  * We can use Express or other backend framework
  * Choice to use UI framework
  * "nuxt generate" to build the app
  
### Products Listing API

* We will use yarn for project development. Of the choices presented we have used the first option from the list

```
$ yarn create nuxt-app products
Programming language: (javascript, typescript)
Package manager: (yarn, npm)
UI framework: (none, ant, balmui, bootstrap vue, chakra ui, buefy, oruga, primevue, tachyons, tailwind css, windi css, vant, view ui, vuetify.js)
Template engine: (html, pug)
Nuxt.js modules: (axios, PWA, git based headless cms)
Linting tools: (eslint, prettier, lint staged files, stylelint, commitlint)
Test framwork: (none, ava, jest, webdriver, nightwatch)
Rendering mode: (universal - ssr/ssg, SPA)
Deployment target: (server, static)
Development tools: (jsconfig.json, semantic pull requests, dependabot)
Continuous integration: (none, github actions, travis ci, circle ci)
Version control: git, none

$ cd products

$ yarn run dev

```

Now, you can view the app that you are building at http://localhost:3000

To get started, remove components/Tutorial.vue and start coding in pages/index.vue. Have fun!

* List of VSCode plugins that can come in handy
  * Vetur

##### Create your first page

Now, create a file about.vue under pages folder and save it
```
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
            title: "Product listing in Nuxt"
            meta: [
                {
                    hid: "description",
                    name: "description about the proudcts app"
                    content: "best place to list your products"
                }
            ]
        }
    }
    
}
</script>
```

The page that you created can be viewed in the URL http://localhost:3000/about

As part of continued learning, we will go ahead and create the following changes to the product listing app
* Use axios to pull product listing data
* Create a single product page to list product specific information and link to it from the product listing page
* Create a search form to do a basic search and display of products based on the search term

**Home page**
![Home Page](./assets/nuxt2-home.jpg)

**Single page product listing**
![Single Page](./assets/nuxt2-singlepage.jpg)