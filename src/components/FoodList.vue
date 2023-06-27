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
                  "photo": "/img/hamburguermeat.png",
                  "name": "Meat Burguer",
                  "price": 5.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/hamburguerchicken.png",
                  "name": "Chicken Burguer",
                  "price": 4.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/hamburguerbacon.png",
                  "name": "Bacon Burguer",
                  "price": 2.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/fries.png",
                  "name": "Fries",
                  "price": 2.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/nuggets.png",
                  "name": "Nuggets",
                  "price": 3.49,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/cookie.png",
                  "name": "cookies",
                  "price": 2.79,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/soda.png",
                  "name": "Mango Soda",
                  "price": 1.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/icetea.png",
                  "name": "Ice Tea",
                  "price": 1.99,
                  "active": false,
                  "quantity": 1
              },
              {
                  "photo": "/img/water.png",
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

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;700&family=Roboto:wght@100;300;400;500;700;900&family=Source+Sans+Pro:wght@200;300;400;600;700;900&display=swap");

body {
  width: 100vw;
  height: 100vh;
  align-items: center;
  justify-content: center;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  background-color: rgb(255, 255, 255);
}

main > section.items h4 {
  text-align: center;
  margin-top: 0;
  width: 100%;
  color: rgb(20, 33, 61);
}
main {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-wrap: wrap;
  padding-top: 20px;
}

main > section.items {
  display: flex;
  flex-wrap: wrap;
  border: 1px solid rgb(229, 229, 229);;
  border-radius: 10px;
  padding: 20px;
  max-width: 500px;
  min-width: 300px;
  justify-content: center;
}

section.items .product {
  border: 1px solid rgb(229, 229, 229);;
  border-radius: 10px;
  margin: 10px;
  flex: 0 0 calc(33.333% - 24px);
  cursor: pointer;
  text-align: center;
}

section.items .product.selected {
  border: 2px solid rgb(252, 163, 17);
}

section.items .photo img {
  max-width: 90px;
  max-height: 90px;
  width: auto;
  height: auto;
}

section.items .description {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  font-size: 11px;
  line-height: 15px;
  color:rgb(20, 33, 61);
}

section.items .description .price {
  font-weight: bold;
  margin: 4px auto;
}

section.items .description .quantity-area {
  margin: 8px auto;
  height: 14px;
}

section.items .description .quantity-area button {
  width: 16px;
  height: 16px;
  display: inline-grid;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

section.items .description .quantity-area .quantity {
  font-weight: bold;
  margin: 0 4px;
}

section.summary {
  background-color: rgb(245, 245, 245);
  padding: 20px;
  min-height: 200px;
  min-width: 200px;
  border-radius: 10px;
  text-align: center;
  position: absolute;
  top: 50%;
  right: 0%;
  transform: translate(-50%, -50%);
}

section.comment {
  background-color: rgb(245, 245, 245);
  padding: 20px;
  min-width: 200px;
  border-radius: 10px;
  text-align: center;
  position: absolute;
  top: 50%;
  left: 19.75%;
  transform: translate(-50%, -50%);
}

section.summary table {
  width: 100%;
  padding-top: 12px;
  font-size: 11px;
  margin: auto;
}

section.summary table tbody tr:last-of-type th {
  border-top: 1px solid rgb(245, 245, 245);
  padding-top: 4px;
}

</style>