<template>
  <div id="app">
    <div>
      <ProductForm :onAddProduct="handleOnAddProduct" />
      <ProductList :listdata="products" />
      <SearchBar :onSearchProduct="handleOnSearchProduct" />
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
      products: [
        {
          name: "iPhone 12",
          price: "50.000,00",
          category: "Celulares",
        },
        {
          name: "iPhone 11",
          price: "39.998,00",
          category: "Celulares",
        },
      ],
    };
  },

  props: {
    onAddProduct: Function,
    listdata: Array,
    onSearchProduct: Function,
  },

  methods: {
    handleOnAddProduct(product) {
      console.log(product);
      this.products = this.products.concat(product);
    },

    handleOnSearchProduct(text) {
      const results = this.products.filter((p) => p.name === "text");
      if (results.length > 0) {
        this.listedProducts = results;
      } else {
        this.listedProducts = this.products;
      }

      console.log(this.listedProducts);
    },
  },
};
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
