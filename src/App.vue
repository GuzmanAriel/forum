<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class="container">
    <RouterView/>
  </div>
</template>

<script>
import PageHome from './pages/Home.vue'

export default {
  name: 'App'
}
</script>

<style>
@import "assets/style.css";
</style>
