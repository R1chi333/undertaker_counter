<script setup>
import chartOne from './chartOne.vue'
import chartTwo from './chartTwo.vue'
</script>
<template>
  <div id="chartsCon">
    <chartOne :cause="cause" :causeTwo="causeTwo" :death="death" :deathTwo="deathTwo" />
    <chartTwo :cause="cause" :causeTwo="causeTwo" :death="death" :deathTwo="deathTwo" />
  </div>
</template>
<style>
#chartsCon {
  background-color: rgb(167, 167, 167);
  width: 75vw;
  height: 45vw;
  border: solid;
  border-color: rgb(112, 112, 112);
  border-width: 0.5vw;
}
</style>
<script>
export default {
  name: 'chartsContainer',
  props: {
    cause: {
      type: String,
      default: ''
    },
    causeTwo: {
      type: String,
      default: ''
    },
    death: {
      type: String,
      default: ''
    },
    deathTwo: {
      type: String,
      default: ''
    }
  }
}
</script>
