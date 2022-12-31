<template>
  <h3>Main properties of browser on your device:</h3>
  <ul v-for="(propertyInfo, index) in propNames">
    <li :key="index">{{ propertyInfo }}</li>
  </ul>
</template>

<script setup>
  const getProperty = (text, propName) => {
    const attention = 'Your browser does not support property/method ';
  
    return text + (new Function('return ' + propName)() || attention + propName);
  };

  const propNames = [
    ['€¥^: ', 'navigator.ui'],
    ['Your browser: ', 'navigator.appName'],
    ['Browser version: ', 'navigator.appVersion'],
    ['Code name of browser: ', 'navigator.appCodeName'],
    ['Platform: ', 'navigator.platform'],
    ['Cookie enabled: ', 'navigator.cookieEnabled'],
    ['UserAgent: ', 'navigator.userAgent']
  ].map(([descr, prop]) => getProperty(descr, prop));
</script>

<style>

</style>