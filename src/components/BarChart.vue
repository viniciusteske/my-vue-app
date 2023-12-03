<template>
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
      :legend="chartLegend"
    />
  </template>
  
  <script>
  import { Bar } from 'vue-chartjs'
  import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
  
  ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)
  
  export default {
    name: 'BarChart',
    components: { Bar },
    data() {
      return {
        chartData: {
          labels: [ 'Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho', 'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro'],
          datasets: [{
            label: 'Peso da Joaninha',
            data: [98, 96, 92, 87, 85, 81, 85, 75, 73, 71, 69, 63],
            backgroundColor: [
            'rgba(255, 99, 132, 1)',
            'rgba(255, 159, 64, 1)',
            'rgba(255, 205, 86, 1)',
            'rgba(75, 192, 192, 1)',
            'rgba(54, 162, 235, 1)',
            'rgba(153, 102, 255, 1)',
            'rgba(201, 203, 207, 1)',
            'rgba(255, 99, 132, 1)',
            'rgba(255, 159, 64, 1)',
            'rgba(255, 205, 86, 1)',
            'rgba(75, 192, 192, 1)',
            'rgba(54, 162, 235, 1)',
            'rgba(153, 102, 255, 1)'
              ]
          },
          {
            label: 'Frequência cardíaca média da Joaninha',
            data: [140, 138, 135, 130, 125, 120, 128, 110, 115, 100, 95, 90],
            backgroundColor: [
            'rgba(75, 192, 192, 0.5)',
            'rgba(255, 99, 132, 0.5)',
            'rgba(200, 205, 140, 0.5)',
            'rgba(54, 162, 235, 0.5)',
            'rgba(255, 159, 64, 0.5)',
            'rgba(255, 102, 255, 0.5)',
            'rgba(255, 87, 34, 0.5)',
            'rgba(75, 192, 192, 0.5)',
            'rgba(255, 99, 132, 0.5)',
            'rgba(255, 205, 86, 0.5)',
            'rgba(54, 162, 235, 0.5)',
            'rgba(255, 159, 64, 0.5)',
              ]
          }]
        },
        chartOptions: {
          responsive: true
        },
        chartLegend: 'Legend'
      }
    }
  }
  </script>