<script lang="ts">
import {
  Chart as ChartJS,
  Filler,
  Legend,
  LineElement,
  PointElement,
  RadialLinearScale,
  Tooltip,
} from 'chart.js'
import { Radar } from 'vue-chartjs'

ChartJS.register(
  RadialLinearScale,
  PointElement,
  LineElement,
  Filler,
  Tooltip,
  Legend,
)

export default {
  name: 'App',
  components: {
    Radar,
  },
  data() {
    return {
      data: {
        labels: [
          'G90',
          'xG90',
          'Sh90',
          'A90',
          'xA90',
          'KP90',
          'xGChain90',
          'xGBuildup90',
        ],
        datasets: [
          {
            label: 'Messi',
            backgroundColor: 'rgba(179,181,198,0.2)',
            borderColor: 'rgba(179,181,198,1)',
            pointBackgroundColor: 'rgba(179,181,198,1)',
            pointBorderColor: '#fff',
            pointHoverBackgroundColor: '#fff',
            pointHoverBorderColor: 'rgba(179,181,198,1)',
            data: [0.89, 0.78, 5.15, 0.44, 0.46, 2.65, 1.29, 0.53],
          },
          {
            label: 'Mitoma',
            backgroundColor: 'rgba(255,99,132,0.2)',
            borderColor: 'rgba(255,99,132,1)',
            pointBackgroundColor: 'rgba(255,99,132,1)',
            pointBorderColor: '#fff',
            pointHoverBackgroundColor: '#fff',
            pointHoverBorderColor: 'rgba(255,99,132,1)',
            data: [0.27, 0.36, 2.03, 0.20, 0.27, 1.56, 0.82, 0.36],
          },
        ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
      },
    }
  },
}
</script>

<template>
  <div>
    <Radar :data="data" :options="options" />
  </div>
</template>
