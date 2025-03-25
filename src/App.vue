<script setup>
import FlipCard from './components/FlipCard.vue';
import PrimeVue from 'primevue/config';
import { createApp } from 'vue';

import 'primevue/resources/themes/saga-blue/theme.css';
import 'primevue/resources/primevue.min.css';
import 'primeicons/primeicons.css';

const app = createApp({});
app.use(PrimeVue);
</script>

<template>
  <div id="app">
    <h1>Flip Card Grid with PrimeVue</h1>
    <FlipCard />
  </div>
</template>

<style scoped>
#app {
  text-align: center;
  margin: 20px;
}

h1 {
  color: #42b983;
  margin-bottom: 20px;
}
</style>