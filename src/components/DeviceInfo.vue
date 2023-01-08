<template>
  <div class="block__wrap">
    <LanguagesInfo />
    <CoreInfo />
    <NavigatorInfo />
    <ConnectionInfo />
    <MemoryInfo />
    <PropertyInfo :header-text="textTouch" :props-array="propsTouch" />
  </div>
</template>

<script setup>
  import LanguagesInfo from '@/LanguagesInfo';
  import CoreInfo from '@/CoreInfo';
  import NavigatorInfo from '@/NavigatorInfo';
  import ConnectionInfo from '@/ConnectionInfo';
  import MemoryInfo from '@/MemoryInfo';
  import PropertyInfo from '@/PropertyInfo';
  
  const textTouch = 'Only for the touch screen:';
  const propsTouch = [['The maximum number of supported simultaneous touch points: ', 'navigator.maxTouchPoints']];
    
</script>

<style>
 .block__item {
   flex: 1;
   min-width: 20rem;
   max-width: 24rem;
   padding: 10px;
 }
 .block__item__wrap {
    background: #F7F7F2;
    position: relative;
 }
 .block__item__wrap:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    background: #C9F2C7;
    transform: rotate(1deg);
    transform-origin: left bottom;
    transition: .3s ease-in-out;
 }
 .block__item__wrap:hover:after {
    top: 5px;
    left: 5px;
    transform: rotate(2deg);
 }
</style>
