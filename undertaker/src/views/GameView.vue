<script setup>
import container from '../components/container.vue'
import guide from '../components/guide.vue'
import back from '../components/back.vue'
</script>

<template>
  <main>
    <back/>
    <guide/>
    <container />
  </main>
</template>
<style scoped>
p {
  color: white;
  text-align: center;
  margin-top: 45vh;
}
</style>
