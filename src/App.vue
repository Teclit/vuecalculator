<template>
  <Header msg="PMN | Simple VueJS project *Calculator"/>
  <calculator></calculator>
</template>

<script>

import Header from './components/Header.vue'
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Header,
    Calculator
  }
}
</script>

<style>
  *, *::before, *::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  background:  #f7f7f7;
}


  
</style>
