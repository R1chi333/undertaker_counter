<script setup>
import questionOne from './questionOne.vue'
import questionTwo from './questionTwo.vue'
import dirtChart from './dirtChart.vue'
import buttonOne from './buttonOne.vue'
import buttonTwo from './buttonTwo.vue'
import chartsContainer from './chartsContainer.vue'
import counter from './counter.vue'
</script>

<template>
  <div>
    <counter :score="score"/>
    <div id="chartsContainer" v-if="showChildComponent">
      <chartsContainer @remove="removeChildComponent" 
      :cause=" cause"
      :causeTwo="causeTwo"
      :death= "death"
      :deathTwo="deathTwo"
      :score="score"
      :year="year"
      :sex="sex"
      :race="race"
      :yearTwo="yearTwo"
      :sexTwo="sexTwo"
      :raceTwo="raceTwo"
      />
      <button @click="removeChildComponent();fetchData();"  id="newRound">{{ moveOn }}</button>
    </div>
    
    <div id="questions">
      <questionOne
      :cause="cause"
      :year="year"
      :sex="sex"
      :race="race"/>
      <questionTwo
      :causeTwo="causeTwo"
      :yearTwo="yearTwo"
      :sexTwo="sexTwo"
      :raceTwo="raceTwo"
      />
    </div>
    <div id="buttons" class="buttons">
      <div @click="addChildComponent(); optionOne()" id="buttonOne" class="buttons">
        <buttonOne/>
      </div>
      <div @click="addChildComponent();optionTwo()" id="buttonTwo" class="buttons">
        <buttonTwo/>
      </div>
    </div>
    <div id="dirt">
      <dirtChart/>
    </div>
  </div>
</template>

<script>
export default {
  components: {
    questionOne,
    questionTwo,
    chartsContainer,
    counter
  },
  data() {
    return {
      moveOn: "NEXT",
      correct: true,
      score: 0,
      cause: "",
      year: "",
      sex: "",
      race: "",
      causeTwo: "",
      yearTwo: "",
      sexTwo: "",
      raceTwo: "",
      death: "",
      deathTwo: "",
      showChildComponent: false
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      if(this.correct === true){
        try {
        const response = await fetch(
          "https://data.cityofnewyork.us/resource/jb7j-dtam.json"
        );
        const data = await response.json();

        const randomIndexOne = Math.floor(Math.random() * data.length);

          this.cause = data[randomIndexOne].leading_cause;
          this.year = data[randomIndexOne].year;
          this.sex = data[randomIndexOne].sex;
          this.race = data[randomIndexOne].race_ethnicity;
          this.death = data[randomIndexOne].deaths;

          const randomIndexTwo = Math.floor(Math.random() * data.length);
          this.causeTwo = data[randomIndexTwo].leading_cause;
          this.yearTwo = data[randomIndexTwo].year;
          this.sexTwo = data[randomIndexTwo].sex;
          this.raceTwo = data[randomIndexTwo].race_ethnicity;
          this.deathTwo = data[randomIndexTwo].deaths;
      } catch (error) {
        console.log(error);
      }
      }
    },
    optionOne(){
      if(parseInt(this.death) >= parseInt(this.deathTwo)){
        this.score++;
        this.correct = true;
        this.moveOn = "NEXT";
      } else{
        this.correct = false;
        this.moveOn = "GAME OVER"
      }
    },
    optionTwo(){
      if(parseInt(this.deathTwo) >= parseInt(this.death)){
        this.score++;
        this.correct = true;
        this.moveOn = "NEXT";
      } else{
        this.correct = false;
        this.moveOn = "GAME OVER"
      }
    },
    addChildComponent() {
      this.showChildComponent = true
    },
    removeChildComponent() {
      if(this.correct === true){
        this.showChildComponent = false
      }
    },
  },
};

</script>

<style scoped>
#newRound{
  position: absolute;
  top: 90%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 1vw;
  background-color: white;
  --b: 3px;   /* border thickness */
  --s: .45em; /* size of the corner */
  --color: #483c34;
  
  padding: calc(.5em + var(--s)) calc(.9em + var(--s));
  color: var(--color);
  --_p: var(--s);
  background:
    conic-gradient(from 90deg at var(--b) var(--b),#0000 90deg,var(--color) 0)
    var(--_p) var(--_p)/calc(100% - var(--b) - 2*var(--_p)) calc(100% - var(--b) - 2*var(--_p));
  transition: .3s linear, color 0s, background-color 0s;
  outline: var(--b) solid #0000;
  outline-offset: .6em;

  border: 0;
  font-family: 'Bevan';
  font-size: .9vw;
  transition-duration: .2s;
}
#newRound:hover{
  font-size: 1vw;
}
#chartsContainer{
  z-index: 999;
  position: absolute;
  top: 25vw;
  left: 50%;
  transform: translate(-50%, -50%);
}
#buttons{
z-index: 3;
position: relative;
display: flex;
margin-top: -20%;

}
.buttons{
  margin-left: 6%;
}
#dirt{
  z-index: 1;
  width: 100vw;
  position: relative;
  z-index: 2;
  margin-top: -14%;
}
#questions{
  display: flex;
  justify-content: center;
  margin-top: -3%;
}
</style>