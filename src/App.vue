<template>
  <div id="app">
    <h1> Flip Card Grid with PrimeVue </h1>
    <newFlip />
    <Gallery />
  </div>
</template>

<script>
import newFlip from './components/NewFlip.vue';
import Gallery from './components/Gallery.vue';

export default {
  name: 'App',
  components: {
    newFlip,
    Gallery,
  },
};
</script>

<style scoped>
</style>
