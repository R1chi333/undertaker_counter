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
        labels: ["Option One", "Option Two"],
        datasets: [
          {
            label: 'DEATHS',
            backgroundColor: ['#483c34','#614f45'],
            hoverBackgroundColor: '#5555',
            data: [this.death, this.deathTwo],
            
          }
        ]
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: { 
      legend: {
        labels: {
          color: "#483c34", 
          font: {
            size: '18' ,
            family: 'Bevan',
          }
        }
      }
    },
        scales: {
    x: {
    ticks: {
      color: "#483c34",
      font: {
        family: 'Bevan',
        size: '14',
      },
    },
      grid: {
        color: '#483c34',
        borderColor: '#483c34'
      }
    },
    y: { 
    ticks: {
      color: "#483c34"
    },
      grid: {
        color: '#483c34',
        borderColor: '#483c34'
      }
    }
  }

      }
    }
  }
}
</script>

<style>
#bar-graph {
  width: 30%;
  color: black;
  height: 70%;
  padding: 3%;
}
</style>
