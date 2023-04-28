<template>
  <div>
    <div id="graveTwo">
     <img src="/grave2.png" alt="">
     <div id="textbox">
      <h3>CAUSE OF DEATH:</h3>
      <p>{{ causeTwo }}</p>
      <h3>YEAR:</h3>
      <p>{{ yearTwo  }}</p>
      <h3>SEX:</h3>
      <p>{{ sexTwo }}</p>
      <h3>RACE/ETHNICITY:</h3>
      <p>{{ raceTwo }}</p>
     </div>
    </div>
  </div>
</template>
<style scoped>
h3,p{
  margin: 0%;
}
#textbox{
color: black;
position: absolute;
top: 17vw;
right: 20%;
font-family: 'Barrio';
font-size: 1.5vw;
width: 19vw;
}
img{
  width: 45vw;
}
p{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: .89vw;
  font-weight: bolder;
}
</style>
<script>
export default {
  props: {
    causeTwo: {
      type: String,
      default: "",
    },
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
  },
};
</script>