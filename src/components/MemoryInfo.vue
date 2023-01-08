<template>
  <div class="block__item">
    <div class="block__item__wrap">
      <h3 class="block__title">Hard memory of your device:</h3>
      <div v-for="(state, index) in deviceMemory" class="block__list">
        <p :key="index" class="block__content">{{ state }}</p>
      </div>
    </div>
  </div>
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