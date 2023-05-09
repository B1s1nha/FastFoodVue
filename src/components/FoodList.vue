<template>
  <main>
    <section class="items">
        <h4>{{message}}</h4>
        <div class="product selected">
          <div class="photo">
            <img src="../assets/img/hamburguermeat.png" />
          </div>
          <div class="description">
            <span class="name">Meat Burguer</span>
            <span class="price">$ 5.99</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/hamburguerchicken.png" />
          </div>
          <div class="description">
            <span class="name">Chicken Burguer</span>
            <span class="price">$ 4.99</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/hamburguerbacon.png" />
          </div>
          <div class="description">
            <span class="name">Bacon Burguer</span>
            <span class="price">$ 2.99</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/fries.png" />
          </div>
          <div class="description">
            <span class="name">Fries</span>
            <span class="price">$ 2.99</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/nuggets.png" />
          </div>
          <div class="description">
            <span class="name">Nuggets</span>
            <span class="price">$ 3.49</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/cookie.png" />
          </div>
          <div class="description">
            <span class="name">Cookie</span>
            <span class="price">$ 2.79</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/soda.png" />
          </div>
          <div class="description">
            <span class="name">Mango Soda</span>
            <span class="price">$ 1.99</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/icetea.png" />
          </div>
          <div class="description">
            <span class="name">Ice Tea</span>
            <span class="price">$ 1.99</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
        <div class="product">
          <div class="photo">
            <img src="../assets/img/water.png" />
          </div>
          <div class="description">
            <span class="name">Water</span>
            <span class="price">$ 1.49</span>
            <div class="quantity-area">
              <button><box-icon name="minus" size="xs"></box-icon></button>
              <span class="quantity">1</span>
              <button><box-icon name="plus" size="xs"></box-icon></button>
            </div>
          </div>
        </div>
      </section>

      <section class="summary">
        <strong>Resumo do pedido</strong>
        <table>
          <thead>
            <tr>
              <th>Item</th>
              <th>Total</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Meat Burguer</td>
              <td>5.99</td>
            </tr>

            <tr>
              <th>Total</th>
              <th>5.99</th>
            </tr>
          </tbody>
        </table>
      </section>
    <section class="comment">
        <box-icon name='quote-alt-left' type='solid' size="xs" ></box-icon>
        Food to buy
        <box-icon name='quote-alt-right' type='solid' size="xs"></box-icon>
        </section>
        </main>
</template>

<script>
export default {
  name: "FoodList",
  data(){
    return{
      message: "Make your food choice!"
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- <style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style> -->
