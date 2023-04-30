<template>
  <div id="pie-chart">
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
        labels: ["Option One", "Option Two"],
        datasets: [
          {
            backgroundColor: ['#483c34','#614f45'],
            data: [this.death, this.deathTwo]
          }
        ]
      },
      chartOptions: {
        plugins: { 
      legend: {
        labels: {
          color: "#483c34", 
          font: {
            size: 14,
            family: 'Bevan',
          }
        }
      }
    },
        responsive: true,
        maintainAspectRatio: false
      }
    }
  }
}
</script>
<style>
#pie-chart{
  width: 30%;
  padding: 3%;
}
</style>