<script setup>
import { Bar } from 'vue-chartjs'
</script>
<template>
  <div id="bar">
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
  </div>
</template>

<script>
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

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: { Bar },
  data() {
    return {
      chartData: {
        labels: ['January', 'February'],
        datasets: [{ data: [40, 20] }]
      },
      chartOptions: {
        responsive: true,
        barThickness: 6
      }
    }
  }
}
</script>
<style scoped>
#bar {
  width: 10vw;
}
</style>
