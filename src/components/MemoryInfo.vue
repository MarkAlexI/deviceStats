<template>
  <h3>Hard memory of your device:</h3>
  <ul v-for="(state, index) in deviceMemory">
    <li :key="index">{{ state }}</li>
  </ul>
</template>

<script setup>
  const getProperty = (text, propName) => {
    const attention = 'Your browser does not support property/method ';

    return text + (new Function('return ' + propName)() || attention + propName);
  };

  const deviceMemory = [
    ['This device memory (GiB of RAM): ', 'navigator.deviceMemory']
    ].map(([descr, prop]) => getProperty(descr, prop));
</script>

<style>

</style>