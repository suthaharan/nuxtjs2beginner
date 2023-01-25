<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="text" placeholder="Search Products ...">
    <input type="submit" value="Search Products">
  </form>
</template>

<script>
export default {
  name: "SearchProducts",
  data(){
    return {
        text: ""
    }
  },
  methods:{
    onSubmit(){
        this.$emit('search-text', this.text);
        this.text = "";
    }
  }
}
</script>
