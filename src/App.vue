<template>
  <div class="app" :class="mode">
    <Header :mode="mode" @toggle="toggle" />
    <Content :mode="mode"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Content from './components/Content.vue'
    export default {
    components: { Header, Content },
      data() {
        return {
          mode: 'light'
        }
      },
      mounted() {
        window.addEventListener('keyup', this.keyPress)
      },
      methods: {
        keyPress(e) {
          if (e.key === 't') {
            this.toggle()
          }
        },
        toggle() {
            this.mode = (this.mode === 'light') ? 'dark' : 'light'
        },
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
    transition: background-color .6s ease;
  }
  .dark {
    background-color: #15202B;
    color: #f3f3f3;
  }
</style>