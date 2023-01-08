<template>
  <div class="block__item">
    <div class="block__item__wrap">
      <h3 class="block__title">{{ headerText }}</h3>
      <div v-for="(state, index) in properties" class="block__list">
        <p :key="index" class="block__content">{{ state }}</p>
      </div>
    </div>
  </div>
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