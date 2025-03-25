<template>
  <div class="order-items">
    <div class="item">
      <span>Eggs</span>
      <button @click="decreaseCount('eggs')">-</button>
      <span>{{ counts.eggs }}</span>
      <button @click="increaseCount('eggs')">+</button>
    </div>

    <div class="item">
      <span>Tortillas</span>
      <button @click="decreaseCount('tortillas')">-</button>
      <span>{{ counts.tortillas }}</span>
      <button @click="increaseCount('tortillas')">+</button>
    </div>

    <div class="item">
      <span>Chocolate</span>
      <button @click="decreaseCount('chocolate')">-</button>
      <span>{{ counts.chocolate }}</span>
      <button @click="increaseCount('chocolate')">+</button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HelloWorld',
  setup() {
    const counts = ref({
      eggs: 0,
      tortillas: 0,
      chocolate: 0
    })

    const increaseCount = (item) => {
      counts.value[item]++
    }

    const decreaseCount = (item) => {
      if (counts.value[item] > 0) {
        counts.value[item]--
      }
    }

    return {
      counts,
      increaseCount,
      decreaseCount
    }
  }
}
</script>


