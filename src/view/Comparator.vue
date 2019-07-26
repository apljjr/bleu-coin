<template>
  <div>
    <navbar nameEnterprise="Bleutest"/>
    <container/>
  </div>
</template>

<script>

import Navbar from '../components/Navbar.vue'
import Container from '../components/Container.vue'

export default {
  name: 'Comparador',
  components: {
      Navbar,
      Container
  }
}
</script>

<style scoped>
</style>
