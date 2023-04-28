<template>
  <div>
    <pie-chart
      :data="chartData"
      :options="chartOptions"
      :cause="cause"
      :causeTwo="causeTwo"
      :death="death"
      :deathTwo="deathTwo"
    ></pie-chart>
  </div>
</template>

<script>
import { Pie } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, ArcElement, CategoryScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale)

export default {
  components: {
    PieChart: Pie
  },
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
  data() {
    return {
      chartData: {
        labels: [this.cause, this.causeTwo],
        datasets: [
          {
            backgroundColor: ['#41B883', '#E46651'],
            data: [this.death, this.deathTwo]
          }
        ]
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false
      }
    }
  }
}
</script>
