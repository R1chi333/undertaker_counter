<template>
  <div>
    <question-one :play="play" @toggle-play="togglePlay"></question-one>
    <question-two :play="play" @toggle-play="togglePlay"></question-two>
  </div>
</template>

<script>
import questionOne from './questionOne.vue'
import questionTwo from './questionTwo.vue'

export default {
  components: {
    questionOne,
    questionTwo
  },
  data() {
    return {
      play: true
    }
  },
  methods: {
    togglePlay() {
      this.play = !this.play
    }
  }
}
</script>
<style scoped>
div {
  /* overflow-y: hidden; */
}
</style>
