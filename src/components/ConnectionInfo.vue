<template>
  <h3>State of browser connection:</h3>
  <ul v-for="(state, index) in browserConnection">
    <li :key="index">{{ state }}</li>
  </ul>
</template>

<script setup>
  const getProperty = (text, propName) => {
    const attention = 'Your browser does not support property/method ';

    return text + (new Function('return ' + propName)() || attention + propName);
  };

  let browserConnection = ['', ''];

  const getNetworkInfo = () => {
    browserConnection = [
      ['Type of network connection: ', 'navigator.connection.type'],
      ['Downlink (Mb/s): ', 'navigator.connection.downlink'],
      ['Downlink maximum (Mb/s): ', 'navigator.connection.downlinkMax'],
      ['Effective round-trip time estimate (ms): ', 'navigator.connection.rtt'],
      ['Effective connection type: ', 'navigator.connection.effectiveType'],
      ['Now are saving data? ', 'navigator.connection.saveData']
    ].map(([descr, prop]) => getProperty(descr, prop));
  }

  navigator.connection.addEventListener('change', getNetworkInfo);

  getNetworkInfo();
</script>

<style>

</style>