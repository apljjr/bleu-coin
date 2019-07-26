<template>
  <div>
    <b-navbar class="backgroudNavbar" type="dark">
      <b-navbar-brand>{{nameEnterprise}}</b-navbar-brand>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    nameEnterprise: String
  }
}
</script>

<style scoped>
  .backgroudNavbar {
    background: #0093ff;
    padding-left: 10%;
    padding-right: 10%;
    font-weight: bold
  }
</style>
