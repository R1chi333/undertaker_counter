<template>
  <transition>
    <div v-if="play" id="questionOne">
      <h3>CHOICE ONE</h3>
      <p>CAUSE:</p>
      <p>YEAR:</p>
      <p>SEX:</p>
      <p>RACE/ETHNICITY:</p>
      <button @click="$emit('toggle-play')">BUTTON</button>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    play: Boolean
  }
}
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  animation: up 2s forwards;
}

@keyframes up {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-40vw);
  }
}
button {
  width: 5vw;
  height: 5vw;
  margin-top: 5vw;
  font-size: 0.5vw;
}
#questionOne {
  position: relative;
  height: 38vw;
  width: 33vw;
  background-color: #cecece;
  border: 1vw solid #696969;
  display: inline-block;
  font-family: 'Barrio';
  vertical-align: top;
  text-align: center;
  z-index: 1;
}
h3 {
  color: #272727;
  font-size: 4vw;
  margin: 0;
  margin-top: 3vw;
  margin-bottom: 2vw;
}
p {
  font-size: 1vw;
  font-family: 'Bevan';
  margin: 0;
  margin-top: 1vw;
  color: #272727;
}
</style>
