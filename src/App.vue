<template>
  <div class="app" :class="mode">
    <Header :mode="mode" @toggle="toggle()" />
    <Content :mode="mode"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Content from './components/Content.vue'
    export default {
    components: { Header, Content },
  }
</script>

<script setup>
  import { useTheme } from './stores/useStore';
  import { storeToRefs } from 'pinia'
  import { onMounted } from 'vue-demi';

  const store = useTheme()
  const {mode} = storeToRefs(store)
  const {keyPress} = store
  const {toggle} = store

  onMounted(() => {
    window.addEventListener('keyup', keyPress)
  })

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
    background-color: #30373f;
    color: #f3f3f3;
  }
</style>