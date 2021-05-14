<template>
  <div id="search">
      <input type="text" v-model="search" placeholder="Buscar produto" v-on:keyup="handleSearch"/>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  
  data() {
    return {
      search: "",
    };
  },

  props: {
    onSearchProduct: Function,
  },

  methods: {
    handleSearch() {
      this.onSearchProduct(this.search);
    },
  },
};
</script>

<style>
  #search{
  float:right;
  padding-left:5px;
  padding-top: 50px;
  font-size:18px;
  height:32px;
  width:260px;
  }
</style>