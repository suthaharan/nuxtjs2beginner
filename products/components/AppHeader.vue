<!-- Please remove this file from your project -->
<template>
  <header class="header">
    <h1 class="title">Products App</h1>
    <ul>
      <li>
        <nuxt-link :to="{name: 'index'}">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to='/about'>About</nuxt-link>
      </li>
      <li>
        <nuxt-link to='/posts'>Posts</nuxt-link>
      </li>
      <li>
        <nuxt-link to='/products'>Products</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
}
</script>

<style>
.header{ display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem; padding-bottom: 1rem; border-bottom: 1px dotted #ccc;}
.header .title{font-size: 3rem; color:#536488;}
.header ul{ display: flex;}
.header a{ display: inline block; background: #333; color: #fff; padding: 0.3rem 1rem; margin-right: 0.5rem;}
</style>
