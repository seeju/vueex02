<template>
  <div id="list">
    <div v-for="(item, index) in products" :key="index">
      <ProductItem :product="item" />
    </div>
    <p>{{ totalProducts }}</p>
  </div>
</template>

<script>
import ProductItem from "./ProductItem";

export default {
  name: "ProductList",

  components: {
    ProductItem,
  },

  props: {
    products: Array,
    item: Object,
  },

  computed: {
    totalProducts() {
      const total = this.products.length;
      return total > 1 ? `Total: ${total} produtos` : `Total: ${total} produto`;
    },
  },
};
</script>

<style>
#list {
  position: absolute;
  top: 10px;
  right: 80px;
  width: 200px;
  height: 100px;
}
</style>