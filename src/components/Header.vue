<template>
  <div>
    <header>
      <h1>{{mode}} Mode</h1>

      <Toggle :mode="mode"/>
      
      <nav>
        <div class="nav-link">Home</div>
        <div class="nav-link">About</div>
        <div class="nav-link">Info</div>
        <div class="nav-link">Contact</div>
      </nav>
    </header>
  </div>
</template>

<script>
import Toggle from "./Toggle.vue";
  export default {
    props: {
        mode: {
            type: String,
            default: "light"
        },
    },
    components: { Toggle }
}
</script>

<style scoped>
  header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding-left: 20px;
    height: 60px;
    background-color: #c3c3c3;
    color: rgb(116, 116, 116);
    transition:  background-color .3s ease-in;
  }
  header h1 {
    font-size: 32px;
    text-transform: uppercase;
    font-weight: 900;
  }
  .dark header {
    background-color: #0a0f14;
  }
  nav {
    display: flex;
    align-items: center;
    flex-direction: row;
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
    background-color: #1f2841;
  }
</style>