<template>
  <h3>Quantity of logical cores on your device:</h3>
  <p v-if="cores">{{ cores }}</p>
  <p v-else>{{ attention }}<span>{{ propName }}</span></p>
</template>

<script setup>
  const cores = navigator.hardwareConcurrency;
  const attention = 'Your browser does not support property/method ';
  const propName = 'navigator.hardwareConcurrency';
</script>

<style>
  
</style>