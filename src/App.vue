<template>
  <div>
    <div class="form">
      <ProductForm :onAddProduct="handleOnAddProduct" />
    </div>
      <SearchBar :onSearchProduct="handleOnSearchProduct" />
      <ProductList :products="listedProducts.length > 0 ? listedProducts : products"/>
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
  },
};
</script>

<style>

</style>
