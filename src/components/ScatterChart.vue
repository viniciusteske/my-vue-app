<template>
    <Scatter :data="data" :options="options"/>
  </template>
  
  <script>
  import {
    Chart as ChartJS,
    LinearScale,
    PointElement,
    LineElement,
    Tooltip,
    Legend
  } from 'chart.js'
  import { Scatter } from 'vue-chartjs'
  
  ChartJS.register(LinearScale, PointElement, LineElement, Tooltip, Legend)
  
  export default {
    name: 'ScatterChart',
    components: {
      Scatter
    },
    data() {
      return {
        data: {
          datasets: [
          {
            label: 'Dados falsos',
            fill: false,
            borderColor: '#f87979',
            backgroundColor: '#f87979',
            data: [
              {
                x: -2,
                y: 4
              },
              {
                x: -1,
                y: 1
              },
              {
                x: 0,
                y: 0
              },
              {
                x: 1,
                y: 1
              },
              {
                x: 2,
                y: 4
              }
            ]
          }]
        },
        options: {
          responsive: true
        }
      };
    }
  }
  </script>