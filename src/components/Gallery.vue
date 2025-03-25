<template>
  <h1>{{ msg }}</h1>
  <div class="row">
    <div class="column">
      <p>Classic Leather Jacket</p>
      <img src="../assets/leather-jacket.jpg" alt="Classic Leather Jacket" />
    </div>
    <div class="column">
      <p>Denim Jacket</p>
      <img src="../assets/denim-jacket.jpg" alt="Denim Jacket" />
    </div>
  </div>
  <div class="row">
    <div class="column">
      <p>Bomber Jacket</p>
      <img src="../assets/bomber-jacket.jpg" alt="Bomber Jacket" />
    </div>
    <div class="column">
      <p>Winter Puffer Jacket</p>
      <img src="../assets/denim-jacket.jpg" alt="Winter Puffer Jacket" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Gallery',
  props: {
    msg: String
  }
}
</script>

<style scoped>
.row {
  display: flex;
  justify-content: space-around;
  margin-bottom: 20px;
}

.column {
  flex: 1;
  text-align: center;
}

img {
  max-width: 100%;
  height: auto;
}
</style>
