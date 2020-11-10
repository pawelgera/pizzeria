<template>
  <div id="app">
    <Cart
      :cartItems="cartItems"
      @clear-cart="clearCart"
      @del-cart-item="deleteCartItem"
    />
    <Pizzas :pizzas="pizzas" @add-pizza="addToCart" />
  </div>
</template>

<script>
import Pizzas from "./components/Pizzas";
import Cart from "./components/Cart";
import { v4 as uuidv4 } from 'uuid';
export default {
  name: "App",
  components: {
    Pizzas,
    Cart,
  },
  data() {
    return {
      msg: "hello",
      cartItems: [],
      pizzas: [
        {
          id: 1,
          name: "Margheritta",
          ingredients: ["sos pomidorowy", "ser mozzarella"],
          hasGluten: true,
          hasLactose: true,
          price: 15,
        },
        {
          id: 2,
          name: "Capricciosa",
          ingredients: ["sos pomidorowy", "ser mozzarella", "szynka"],
          hasGluten: true,
          hasLactose: true,
          price: 18,
        },
        {
          id: 3,
          name: "Pepperoni Bez Glutenu",
          ingredients: ["sos pomidorowy", "ser mozzarella", "salami pepperoni"],
          hasGluten: false,
          hasLactose: true,
          price: 25,
        },
        {
          id: 4,
          name: "Hawajska Bez Glutenu i Bez Laktozy",
          ingredients: ["sos pomidorowy", "ser mozzarella", "ananas"],
          hasGluten: false,
          hasLactose: false,
          price: 30,
        },
      ],
    };
  },
  methods: {
    addToCart(pizza) {
      const newCartItem = {
        cartItemId: uuidv4(),
        name: pizza.name,
        id: pizza.id,
        ingredients: pizza.ingredients,
        hasGluten: pizza.hasgluten,
        hasLactose: pizza.haslactose,
        price: pizza.price
      }
      this.cartItems = [...this.cartItems, newCartItem];
    },
    clearCart() {
      this.cartItems = [];
    },
    deleteCartItem(id) {
      this.cartItems = this.cartItems.filter(
        (item) => item.cartItemId != id
      );
    },
  },
};
</script>

<style>
</style>
