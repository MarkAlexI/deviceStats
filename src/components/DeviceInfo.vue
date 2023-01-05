<template>
  <div>
    <h2>Info</h2>
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
  h2 {
    font-size: 1.5rem;
    color: mediumpurple;
    padding-bottom: 8px;
  }
  
  button {
    display: block;
    color: darkblue;
    outline: none;
    font-size: 20px;
    padding: 10px 50px;
  
    &.primary {
      border-color: black;
      background-color: yellow;
    }
  }
</style>
