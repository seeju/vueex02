<template>
  <div>
    <div>
      <ProductItem :item="product" />
      <ul>
        <li v-for="product in listdata" :key="product.name">
          {{ product.name }}<br />{{ product.price }}<br />{{
            product.category
          }}
        </li>
      </ul>
        {{ totalProducts }}
    </div>
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
    listdata: Array,
    item: Object,
  },

  computed: {
    totalProducts() {
      const total = this.listdata.length;
      return total > 1 ? `Total: ${total} produtos` : `Total: ${total} produto`;
    },
  },

};
</script>