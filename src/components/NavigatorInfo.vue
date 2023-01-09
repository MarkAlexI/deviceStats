<template>
  <div class="block__item">
    <div class="block__item__wrap">
      <h3 class="block__title">Main properties of browser on your device:</h3>
      <div v-for="(propertyInfo, index) in propNames" class="block__list">
        <p :key="index" class="block__content">{{ propertyInfo }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
  const getProperty = (text, propName) => {
    const attention = 'Your browser does not support property/method ';
  
    return text + (new Function('return ' + propName)() || attention + propName);
  };

  const propNames = [
    ['Navigator do not track user actions: ', 'navigator.doNotTrack'],
    ['Your browser: ', 'navigator.appName'],
    ['Browser version: ', 'navigator.appVersion'],
    ['Code name of browser: ', 'navigator.appCodeName'],
    ['Current OSCPU: ', 'navigator.oscpu'],
    ['Platform: ', 'navigator.platform'],
    ['Cookie enabled: ', 'navigator.cookieEnabled'],
    ['UserAgent: ', 'navigator.userAgent']
  ].map(([descr, prop]) => getProperty(descr, prop));
</script>

<style>

</style>