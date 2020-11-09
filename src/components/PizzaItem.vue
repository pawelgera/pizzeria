<template>
  <div class="pizza-item">
    <p>{{ pizza.name }}</p>
    <button @click="$emit('add-pizza', pizza)">Dodaj do koszyka</button>
  </div>
</template>
<script>
export default {
  name: "PizzaItem",
  props: ["pizza"]
};
</script>

<style scoped>
</style>