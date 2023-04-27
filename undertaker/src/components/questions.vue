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
      if (this.play === true){
        this.play = false
      } else{
        this.play = true
      }
    },
    fetchRandomRecord() {
      const randomIndex = Math.floor(Math.random() * this.deaths.length);
      this.cause = this.deaths[randomIndex].leading_cause;
      this.year = this.deaths[randomIndex].year;
      this.sex = this.deaths[randomIndex].sex;
      this.race = this.deaths[randomIndex].race_ethnicity;
    }
  }
}
</script>
<style scoped>
div {
  /* overflow-y: hidden; */
}
</style>
