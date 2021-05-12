<template>
  <div>
    <h4>{{ product.name }}</h4>
    <p>R${{ product.price }}</p>
    <p>{{ product.category }}</p>
  </div>
</template>

<script>
export default {
  name: "ProductItem",

  props: {
    product: Object,
  },
};
</script>