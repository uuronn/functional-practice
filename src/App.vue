<template>
  <div>
    
    <Test/>
  </div>
</template>

<script>
import Test from './components/Test.vue'

export default {
    el: '#app',
    components: {
      Test
    },
    data() {
      return {
        active01: false,
      }
    }
}

</script>

<style>

</style>
