<template>
  <div>
    <h2>Koszyk</h2>
    <button @click="$emit('clear-cart')">
      Wyczyść koszyk
    </button>
    <div v-for="item in items" :key="item.id">
      {{ item.name }} {{ item.price }}
    </div>
    <p>Wartość Koszyka: {{ getItemsTotal() }}</p>
  </div>
</template>

<script>
export default {
  name: "Cart",
  props: ["items"],
  emits: ['clear-cart'],
  methods: {
    getItemsTotal() {
      return this.items.reduce((total, item) => total + item.price, 0)
    },
  },
};
</script>

<style scoped>
</style>