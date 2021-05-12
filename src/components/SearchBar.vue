<template>
  <div>
      <input type="text" v-model="search" placeholder="Buscar" v-on:keyup="handleSearch"/>
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