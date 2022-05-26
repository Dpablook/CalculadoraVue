<template>
<div id="App">
  <img alt="Vue logo" src="./assets/logo.png">
  <CalculadoraGreen/>
</div>
</template>

<script>
import CalculadoraGreen from './components/CalculadoraGreen.vue';

export default {
  name: 'App',
  components: {
    CalculadoraGreen,
  }
}
</script>
