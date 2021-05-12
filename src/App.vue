<template>
  <div id="app">
    <div>
      <ProductForm :onAddProduct="handleOnAddProduct" />
      <SearchBar :onSearchProduct="handleOnSearchProduct" />
      <ProductList :products="listedProducts.length > 0 ? listedProducts : products"/>
    </div>
  </div>
</template>

<script>
import ProductForm from "./components/ProductForm";
import ProductList from "./components/ProductList";
import SearchBar from "./components/SearchBar";

export default {
  components: {
    ProductForm,
    ProductList,
    SearchBar,
  },
  data() {
    return {
      products: [],
      listedProducts: [],
    };
  },


  methods: {
    handleOnAddProduct(product) {
      this.products = this.products.concat(product);
    },

    handleOnSearchProduct(text) {
      const results = this.products.filter((p) => p.name.startsWith(text));
      if (results.length > 0) {
        this.listedProducts = results;
      } else {
        this.listedProducts = this.products;
      }
    },

  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
