<template>
  <h3>Main properties of browser on your device:</h3>
  <ul v-for="(property, index) in propNames">
  <li :key="index">{{ property }}</li>
  </ul>
</template>

<script setup>

   const code = navigator.appCodeName;
   const name = navigator.appName;
   const version = navigator.appVersion;
   const platform = navigator.platform;
   const cook = navigator.cookieEnabled;
   const userAgent = navigator.userAgent;
   
   const propNames = ['Your browser: ' + name,
      'Browser version: ' + version,
      'Code name of browser: ' + code,
      'Platform: ' + platform,
      'Cookie enabled: ' + cook,
      'UserAgent: ' + userAgent];

</script>

<style>
  
</style>