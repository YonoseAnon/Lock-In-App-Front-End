<template>
    <div class="grid-container">
      <div
        v-for="card in cards"
        :key="card.id"
        class="card-wrapper"
        :class="{ flipped: card.flipped }"
        @click="flipCard(card.id)"
      >
        <Card class="card front">
          <template #header>
            <h3>{{ card.title }}</h3>
          </template>
          <template #content>
            <p>{{ card.frontContent }}</p>
          </template>
        </Card>
        <Card class="card back">
          <template #content>
            <p>{{ card.backContent }}</p>
          </template>
        </Card>
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
      const cards = ref([
        { id: 1, title: 'Card 1', frontContent: 'Front of Card 1', backContent: 'Back of Card 1', flipped: false },
        { id: 2, title: 'Card 2', frontContent: 'Front of Card 2', backContent: 'Back of Card 2', flipped: false },
        { id: 3, title: 'Card 3', frontContent: 'Front of Card 3', backContent: 'Back of Card 3', flipped: false },
        { id: 4, title: 'Card 4', frontContent: 'Front of Card 4', backContent: 'Back of Card 4', flipped: false },
        { id: 5, title: 'Card 5', frontContent: 'Front of Card 5', backContent: 'Back of Card 5', flipped: false },
        { id: 6, title: 'Card 6', frontContent: 'Front of Card 6', backContent: 'Back of Card 6', flipped: false },
        { id: 7, title: 'Card 7', frontContent: 'Front of Card 7', backContent: 'Back of Card 7', flipped: false },
        { id: 8, title: 'Card 8', frontContent: 'Front of Card 8', backContent: 'Back of Card 8', flipped: false }
      ]);
  
      function flipCard(id) {
        const card = cards.value.find(c => c.id === id);
        if (card) {
          card.flipped = !card.flipped;
        }
      }
  
      return { cards, flipCard };
    }
  };
  </script>
  
  <style scoped>
  .grid-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
    justify-items: center;
    margin: 20px;
  }
  

  .card-wrapper {
    position: relative;
    width: 150px;
    height: 200px;
    transform-style: preserve-3d;
    transition: transform 0.6s;
  }
  

  .card-wrapper.flipped {
    transform: rotateY(180deg);
  }
  
  .card {
    width: 100%;
    height: 100%;
    position: absolute;
    backface-visibility: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
  
  .front {
    background: black;
    border: 1px solid white;
    color: white;
  }
  
  .back {
    background: white;
    color: red;
    transform: rotateY(180deg);
  }
  </style>
  