<template>
  <div>
    {{ item.name }} {{ item.price }}
    <button @click="$emit('del-cart-item', item.cartItemId)">Delete</button>
  </div>
</template>

<script>
export default {
  name: "CartItem",
  props: ["item"],
  emits: ["del-cart-item"],
};
</script>

<style scoped>
</style>