<template>
  <div id="app">
    <Cart :items="items" @add-pizza="$emit('add-to-cart',pizza)" />
    <Pizzas :pizzas="pizzas"/>

  </div>
</template>

<script>
import Pizzas from './components/Pizzas';
import Cart from './components/Cart'
export default {
  name: "App",
  components: {
    Pizzas,
    Cart
  },
  data() {
    return {
      msg:'hello',
      items: [],
      pizzas: [
        {
          id: 1,
          name: "Margheritta",
          ingrediens: ['sos pomidorowy, ser mozzarella'],
          hasgluten: true,
          haslactose: true,
          price: 15
        },
        {
          id: 2,
          name: "Capricciosa",
          ingrediens: ['sos pomidorowy', 'ser mozzarella','szynka'],
          hasgluten: true,
          haslactose: true,
          price: 18
        },
        {
          id: 3,
          name: "Pepperoni Bez Glutenu",
          ingrediens: ['sos pomidorowy', 'ser mozzarella','salami pepperoni'],
          hasgluten: false,
          haslactose: true,
          price: 25
        },
        {
          id: 4,
          name: "Hawajska Bez Glutenu i Bez Laktozy",
          ingrediens: ['sos pomidorowy', 'ser mozzarella','ananas'],
          hasgluten: false,
          haslactose: false,
          price: 30
        }
      ]
    };
  },
  methods: {
    addToCart(pizza){
      this.items += pizza
    }
  }
};
</script>

<style>
</style>
