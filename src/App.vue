<template>
  <div class="app" :class="mode">
    <Header :mode="mode"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
  export default {
  components: { Header },
    data() {
      return {
        mode: 'light'
      }
    },
  }
</script>

<style scoped>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
  }
  .app {
    width: 100vw;
    min-height: 100vh;
    background-color: #f3f3f3;
  }
  .dark {
    background-color: #15202B;
    color: #f3f3f3;
  }
</style>