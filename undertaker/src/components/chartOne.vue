<script setup>
import { Bar } from 'vue-chartjs'
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
} from 'chart.js'
</script>
<template>
  <div id="bar-graph">
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
      :cause="cause"
      :causeTwo="causeTwo"
      :death="death"
      :deathTwo="deathTwo"
      :border="800"
    />
  </div>
</template>

<script>
ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
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
  },
  components: { Bar },
  data() {
    return {
      chartData: {
        labels: [this.cause, this.causeTwo],
        datasets: [{ data: [this.death, this.deathTwo] }]
      },
      chartOptions: {
        responsive: true,
        barThickness: 20
      },
      options: {
        border: {
          width: 200
        }
      }
    }
  }
}
</script>

<style>
#bar-graph {
  width: 30vw;
}
</style>
