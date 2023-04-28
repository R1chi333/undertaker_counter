<template>
  <div>
    <div id="graveOne">
     <img src="/grave1.png" alt="">
     <div id="textbox">
      <h3>CAUSE OF DEATH:</h3>
      <p>{{ cause }}</p>
      <h3>YEAR:</h3>
      <p>{{ year  }}</p>
      <h3>SEX:</h3>
      <p>{{ sex }}</p>
      <h3>RACE/ETHNICITY:</h3>
      <p>{{ race }}</p>
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
top: 16vw;
left: 20%;
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
    cause: {
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
  },
};
</script>