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
        message1: "nothing",
    }
  },
}
</script>

