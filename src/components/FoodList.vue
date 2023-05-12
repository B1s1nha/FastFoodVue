<template>
  <main>
    <section class="items">
      <h4>{{ message }}</h4>
      <div 
      v-for="product in products" 
      :key="product.id" 
      class="product"
      v-on:click="product.active = !product.active"
      :class="product.active ? 'selected' : ''"
      >
        <div class="photo">
          <img :src="product.photo" />
        </div>
        <div class="description">
          <span class="name"> {{ product.name }} </span>
          <span class="price">{{ product.price }}</span>
          <div class="quantity-area" v-if="product.active">
            <button v-on:click.stop="product.quantity = product.quantity - 1" :disabled="product.quantity <= 1">-</button>
            <span class="quantity">{{ product.quantity }}</span>
            <button v-on:click.stop="product.quantity = product.quantity + 1">+</button>
          </div>
        </div>
      </div>
    </section>

    <section class="summary" v-if="total()>0">
      <strong>Order Details</strong>
      <table>
        <thead>
          <tr>
            <th>Item</th>
            <th>Total</th>
          </tr>
        </thead>
        <tbody>
          <tr 
          v-for="product in products"
          :key="product.id"
          >
            <template v-if="product.active">
                <td>{{ product.quantity + 'x ' + product.name }}</td>
                <td>{{ (product.price * product.quantity).toFixed(2) }}</td>
            </template>
            
          </tr>

          <tr>
            <th>Total</th>
            <th>{{ total() }}</th>
          </tr>
        </tbody>
      </table>
    </section>
  </main>
</template>

<script>
export default {
  name: "FoodList",
  data() {
    return {
      message: "Make your food choice!",
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
    },
   methods: {
        total: function(){
          var total = 0;
           this.products.forEach(function(item){
            if (item.active) {
              total += item.price * item.quantity;
            }
           });
           return total.toFixed(2);
        }
  },
};
</script>
