<template>
  <div class="content">
    <h2>This is {{mode}} mode</h2>
    <div class="image-grid">
      <div class="col">
        <img src="https://images.unsplash.com/photo-1648391956247-f3c074404e7f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80">
      </div>
      <div class="col">
        <img src="https://images.unsplash.com/photo-1645363710675-c72dae0ea38c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=854&q=80">
      </div>
      <div class="col">
        <img src="https://images.unsplash.com/photo-1630333789027-009e9003507e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80">
      </div>
    </div>
    <div class="text">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, debitis natus laudantium cum neque laborum atque unde. Rerum illum corporis voluptatem quas doloribus laborum? Eos numquam neque reprehenderit maxime earum?
    </div>
  </div>
</template>

<script setup>
  import { useTheme } from '../stores/useStore';
  import { storeToRefs } from 'pinia';

  const store = useTheme()
  const {mode} = storeToRefs(store)
</script>

<style scoped>
  .content {
    padding: 25px;
  }
  .col {
    height: 20vw;
    overflow: hidden;
  }
  img {
    width: 100%;
  }
  h2 {
    font-size: 28px;
    text-transform: uppercase;
    font-weight: 300;
    margin-bottom: 20px;
  }
  .image-grid {
    display: grid;
    grid-template-columns: repeat(3, auto);
    gap: 10px;
    grid-auto-rows: 1fr;
  }
  .text {
    width: 100%;
    max-width: 700px;
    margin-top: 25px;
  }
</style>