<template>
  <div>
    <h2>Koszyk</h2>
    <p>Wartość Koszyka: {{ getItemsTotal() }}</p>
    <button @click="$emit('clear-cart')">Wyczyść koszyk</button>
    <ul>
      <li v-for="item in cartItems" :key="item.id">
        <CartItem :item="item" @del-cart-item="$emit('del-cart-item', item.cartItemId)" />
      </li>
    </ul>
  </div>
</template>

<script>
import CartItem from "./CartItem";
export default {
  name: "Cart",
  components: {
    CartItem,
  },
  props: ["cartItems"],
  emits: ["clear-cart", "del-cart-item"],
  methods: {
    getItemsTotal() {
      return this.cartItems.reduce((total, cartItem) => total + cartItem.price, 0);
    },
  },
};
</script>

<style scoped>
</style>