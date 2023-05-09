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
  }
}
</script>


<!-- <style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style> -->
