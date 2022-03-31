<template>
  <div>
    <header>
      <h1>{{mode}} Mode</h1>
      <Toggle :mode="mode" @toggle="$emit('toggle')"/>
      
      <nav>
        <div class="nav-link">Home</div>
        <div class="nav-link">About</div>
        <div class="nav-link">Info</div>
        <div class="nav-link">Contact</div>
      </nav>
    </header>
  </div>
</template>

<script setup>
  import Toggle from "./Toggle.vue";
  import { useTheme } from '../stores/useStore';
  import { storeToRefs } from 'pinia';

  const store = useTheme()
  const {mode} = storeToRefs(store)
</script>

<style scoped>
  header {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding-left: 20px;
    height: 60px;
    background-color: #dadada;
    color: rgb(29, 29, 29);
    transition:  background-color .6s ease-in;
  }
  header h1 {
    font-size: 32px;
    text-transform: uppercase;
    font-weight: 900;
    margin-right: 20px;
  }
  .dark header {
    background-color: #0a0f14;
    color: #fff;
  }
  nav {
    display: flex;
    align-items: center;
    flex-direction: row;
    margin-left: auto;
  }
  .nav-link {
    display: flex;
    align-items: center;
    height: 60px;
    padding: 0 15px;
  }
  .nav-link:hover {
    cursor: pointer;
    background-color: #b0b0b0;
  }
  .dark .nav-link:hover {
    background-color: #829ce4;
  }
  .toggler {
    margin-right: auto;
  }

</style>