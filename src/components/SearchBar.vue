<template>
  <form v-on:submit.prevent="onHandleSearch">
    <input type="text" v-model="search" /><button type="submit">Buscar</button>
  </form>
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
    onHandleSearch() {
        this.onSearchProduct(this.search);
    }
    
  }
};
</script>