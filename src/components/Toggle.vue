<template>
  <div class="toggle-wrapper">
    <label class="toggle">
      <input 
        type="checkbox" 
        :checked="(mode === 'dark') ? true : false"
        @change="toggle"
      >
      <span class="toggler round"></span>
    </label>
  </div>
</template>

<script setup>
  import { useTheme } from '../stores/useStore';
  import { storeToRefs } from 'pinia';

  const store = useTheme()
  const {mode} = storeToRefs(store)
  const {toggle} = store

</script>

<style>
  .toggle {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
  }
  .toggle input {
    opacity: 0;
    width: 0;
    height: 0;
  }
  .toggler {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    background-color: #15202B;
    transition: .4s;
    cursor: pointer;
  }
  .toggler::before {
    position: absolute;
    content: '';
    height: 26px;
    width: 26px;
    top: 4px;
    left: 4px;
    background-color: #fff;
    transition: .4s;
  }
  input:checked + .toggler {
    background-color: #2196F3;
  }
  input:focus + .toggler {
    box-shadow: 0 0 2px #2196F3;
  }
  input:checked + .toggler::before {
    transform: translateX(26px);
  }
  .round {
    border-radius: 40px;
  }
  .round::before {
    border-radius: 40px;
  }
</style>