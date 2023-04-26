<script setup>
import chartOne from './chartOne.vue'
</script>

<template>
  <div id="conn">
    <p>charts and shit idk</p>
    <chart-one />
    <button @click="$emit('toggle-off')">OKAY</button>
  </div>
</template>
<style scoped>
#conn {
  position: absolute;
  width: 68vw;
  height: 38vw;
  margin: auto;
  background-color: #cecece;
  top: 0vw;
  z-index: 0;
  border: 1vw solid #696969;
  margin-top: 5vw;
}
</style>
