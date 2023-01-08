<template>
  <div class="block__item">
    <div class="block__item__wrap">
      <h3 class="block__title">Quantity of logical cores on your device:</h3>
      <p v-if="cores" class="block__content">{{ cores }}</p>
      <p v-else class="block__content">{{ attention }}<span>{{ propName }}</span></p>
    </div>
  </div>
</template>

<script setup>
  const cores = navigator.hardwareConcurrency;
  const attention = 'Your browser does not support property/method ';
  const propName = 'navigator.hardwareConcurrency';
</script>

<style>
  
</style>