<template>
  <div class="card-grid">
    <div v-for="card in cards" :key="card.id" class="flip-card" @click="flipCard(card.id)">
      <div class="flip-card-inner" :class="{ flipped: card.flipped }">
        <div class="flip-card-front">
          <Card>
            <template #title>{{ card.title }}</template>
            <template #content>
              <p>{{ card.frontContent }}</p>
            </template>
          </Card>
        </div>
        <div class="flip-card-back">
          <Card>
            <template #title>{{ card.title }}</template>
            <template #content>
              <p>{{ card.backContent }}</p>
            </template>
          </Card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import Card from 'primevue/card';

export default {
  name: 'FlipCardGrid',
  components: { Card },
  setup() {
    const cards = ref([...Array(8).keys()].map(i => ({
      id: i + 1,
      title: `Card ${i + 1}`,
      frontContent: `Front of Card ${i + 1}`,
      backContent: `Back of Card ${i + 1}`,
      flipped: false,
    })));

    function flipCard(id) {
      const card = cards.value.find(c => c.id === id);
      if (card) {
        card.flipped = !card.flipped;
      }
    }

    return { cards, flipCard };
  },
};
</script>

<style scoped>
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}
.flip-card {
  perspective: 1000px;
  cursor: pointer;
}
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 200px;
  transition: transform 0.6s ease;
  transform-style: preserve-3d;
}
.flip-card-inner.flipped {
  transform: rotateY(180deg);
}
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}
.flip-card-back {
  transform: rotateY(180deg);
}
</style>