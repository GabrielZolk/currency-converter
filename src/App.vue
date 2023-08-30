<template>
  <div id="app">
    <Conversor />
  </div>
</template>

<script>
import Conversor from './components/Conversor.vue';

export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>
