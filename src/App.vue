<template>
  <div id="app">
    <TheNavBar />
    <div class="container">
      <router-view />
    </div>
  </div>
</template>

<script>
import TheNavbar from '@/components/TheNavbar';
export default {
  components: {
    TheNavbar
  }
};
</script>

<style>
@import 'assets/styles.css';
</style>
