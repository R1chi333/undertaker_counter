<template>
    <p id="score">score: {{ score }}</p>
</template>
<style scoped>
#score{
    color: white;
    position: fixed;
    top: 0%;
    left: 50%;
  transform: translate(-50%, -50%);
}
</style>

<script>
export default {
    props: {
    score: {
      type: Number,
      default: 0,
    }
}
}
</script>