<template>
  <div class="pizza-item">
    <p>{{ pizza.name }}</p>
    <p>Cena: {{pizza.price}}, Składniki:</p>
    <ul>
      <li v-for="ingredient in pizza.ingredients" :key="ingredient">{{ingredient}}</li>
    </ul>
    <button @click="$emit('add-pizza', pizza)">Dodaj do koszyka</button>
  </div>
</template>
<script>
export default {
  name: "PizzaItem",
  props: ["pizza"],
  emits: ["add-pizza"]
};
</script>

<style scoped>
</style>