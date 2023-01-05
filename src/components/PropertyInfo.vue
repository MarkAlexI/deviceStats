<template>
  <h3>{{ headerText }}</h3>
  <ul v-for="(state, index) in properties">
    <li :key="index">{{ state }}</li>
  </ul>
</template>

<script setup>
  const props = defineProps({
    headerText: {
      type: String,
      required: true,
      default: 'Browser stats'
    },
    propsArray: {
      type: Array,
      required: true,
      default: () => [['', '']],
    }
  });

  const getProperty = (text, propName) => {
    const attention = 'Your browser does not support property/method ';

    return text + (new Function('return ' + propName)() || attention + propName);
  };
  
  const properties = props.propsArray.map(([descr, prop]) => getProperty(descr, prop));
</script>

<style>

</style>