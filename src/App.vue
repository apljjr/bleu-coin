<template>
  <div id="app">
    <comparator/>
  </div>
</template>

<script>

import Comparator from './view/Comparator.vue'

export default {
  name: 'app',
  components: {
    Comparator
  }
}
</script>

<style>
#app {
  font-family: Helvetica;
  text-align: center;
  color: #7d7d7d;
}
</style>
