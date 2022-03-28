<template>
  <div class="toggle-wrapper">
    <label class="toggle">
      <input type="checkbox" :checked="(mode === 'dark') ? true : false">
      <span class="toggler round"></span>
    </label>
  </div>
</template>

<script>
  export default {
    props: {
      mode: {
        type: String
      },
    },

  }
</script>

<style>
  .toggle {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
    background-color: orange;
  }
</style>