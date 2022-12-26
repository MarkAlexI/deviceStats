<template>
  <div>
    <h2>Info</h2>
    <button class="primary" @click="press">Press me</button>
  </div>
</template>

<script setup>
  const press = () => document.body.style.backgroundColor = 'red';
</script>

<style>
  h2 {
    font-size: 1.5rem;
    color: mediumpurple;
    padding-bottom: 8px;
  }
  
  button {
    display: block;
    color: darkblue;
    outline: none;
    font-size: 20px;
    padding: 10px 50px;
  
    &.primary {
      border-color: black;
      background-color: yellow;
    }
  }
</style>
