<template>
  <div>
    <h2>Koszyk</h2>
    <div v-for="item in items" :key="item.name">
        {{item.name}}
    </div>
  </div>
</template>

<script>
export default {
  name: "Cart",
  props: ["items"],
};
</script>

<style scoped>
</style>