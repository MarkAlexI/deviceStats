<template>
  <div class="block__item">
    <div class="block__item__wrap">
      <h3 class="block__title">State of browser connection:</h3>
      <div v-for="(state, index) in browserConnection" class="block__list">
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

  let browserConnection = ['', ''];

  const getNetworkInfo = () => {
    browserConnection = [
      ['Your browser is now online: ', 'navigator.onLine'],
      ['Type of network connection: ', 'navigator.connection?.type'],
      ['Downlink (Mb/s): ', 'navigator.connection?.downlink'],
      ['Downlink maximum (Mb/s): ', 'navigator.connection?.downlinkMax'],
      ['Effective round-trip time estimate (ms): ', 'navigator.connection?.rtt'],
      ['Effective connection type: ', 'navigator.connection?.effectiveType'],
      ['Now are saving data? ', 'navigator.connection?.saveData']
    ].map(([descr, prop]) => getProperty(descr, prop));
  }

  navigator.connection?.addEventListener('change', getNetworkInfo);

  getNetworkInfo();
</script>

<style>

</style>