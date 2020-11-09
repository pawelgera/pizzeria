<template>
  <div>
    <h2>Pizze</h2>
    <div v-for="pizza in pizzas" :key="pizza.id">
      <PizzaItem :pizza="pizza" @add-pizza="$emit('add-pizza', pizza)" />
    </div>
  </div>
</template>

<script>
import PizzaItem from "./PizzaItem";

export default {
  name: "Pizzas",
  components: {
    PizzaItem,
  },
  props: ["pizzas"],
};
</script>

<style scoped>
</style>