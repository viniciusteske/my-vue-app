<template>
    <div>
        <scatter 
            :data="chartData"
            :options="chartOptions"
        ></scatter> 
    </div>
</template>

<script>
import { Scatter } from 'vue-chartjs';
import { Chart, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js';

Chart.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale);

export default {
    name: 'ScatterPlot',
    components: { Scatter },
    data () {
        return {
            chartData: {
                datasets: [
                    {
                        label: 'Scatter Plot Example',
                        borderColor: 'rgba(75, 192, 192, 1)',
                        backgroundColor: 'rgba(75, 192, 192, 0.2)',
                        data: [
                            {x: 10, y: 20},
                            {x: 15, y: 25},
                        ]
                    }
                ]
            },
            chartOptions: {
                scales: {
                    x: {
                        type: 'linear',
                        position: 'bottom'
                    },
                    y: {
                        type: 'linear',
                        position: 'left'
                    }
                }
            }
        };
    }
}
</script>