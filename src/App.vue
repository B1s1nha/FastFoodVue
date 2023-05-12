<template>
  <div>
  <FoodList/>
  </div>
</template>

<script>
import FoodList from './components/FoodList.vue'

export default {
  name: 'App',
  components: {
    FoodList
  },
  data() {
    return {
        products: [
              {
                  "photo": "../assets/img/hamburguermeat.png",
                  "name": "Meat Burguer",
                  "price": 5.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/hamburguerchicken.png",
                  "name": "Chicken Burguer",
                  "price": 4.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/hamburguerbacon.png",
                  "name": "Bacon Burguer",
                  "price": 2.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/fries.png",
                  "name": "Fries",
                  "price": 2.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/nuggets.png",
                  "name": "Nuggets",
                  "price": 3.49,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/cookies.png",
                  "name": "cookies",
                  "price": 2.79,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/soda.png",
                  "name": "Mango Soda",
                  "price": 1.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/icetea.png",
                  "name": "Ice Tea",
                  "price": 1.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "../assets/img/water.png",
                  "name": "Water",
                  "price": 1.49,
                  "active": false,
                  "quantity": 1
              }
        ],
    }
  }
}
</script>

