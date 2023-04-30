<script setup>
import chartOne from './chartOne.vue'
import chartTwo from './chartTwo.vue'
</script>
<template>
  <div>
    <div id="chartsCon">
      <div id="info">
        <p >Option One: {{ cause }}<br/>YEAR: {{ year }}<br/>SEX: {{ sex }}<br/>RACE: {{ race }}<br/>Total death: {{ death }}<br/><br/>Option Two: {{ causeTwo }}<br/>YEAR: {{ yearTwo }}<br/>SEX: {{ sexTwo }}<br/>RACE: {{ raceTwo }}<br/>Total death: {{ deathTwo }}</p>
        <p id="score">SCORE:  {{score}}</p>
      </div>
    <chartOne :cause="cause" :causeTwo="causeTwo" :death="death" :deathTwo="deathTwo" />
    <chartTwo :cause="cause" :causeTwo="causeTwo" :death="death" :deathTwo="deathTwo" />
  </div>
  </div>
</template>
<style>
#score{
  text-align: center;
}
#info{
  color: #483c34;
  padding-left: 5%;
  font-family: 'Bevan';
  width: 35%;
  font-size: 1vw;
}
#chartsCon {
  background-color: #928177;
  width: 75vw;
  height: 45vw;
  border: solid;
  border-color: rgb(49, 41, 41);
  border-width: 0.9vw;
  display: flex;
  align-items: center;
  justify-content: space-between;
  animation-duration: 2s;
  animation-fill-mode: forwards;
}
</style>
<script>
export default {
  name: 'chartsContainer',
  props: {
    yearTwo: {
      type: String,
      default: "",
    },
    sexTwo: {
      type: String,
      default: "",
    },
    raceTwo: {
      type: String,
      default: "",
    },
    year: {
      type: String,
      default: "",
    },
    sex: {
      type: String,
      default: "",
    },
    race: {
      type: String,
      default: "",
    },
    score: {
      type: Number,
      default: 0,
    },
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
