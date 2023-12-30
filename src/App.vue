<script setup lang="ts">
import { Line, Pie } from "vue-chartjs"
import { Chart as ChartJS, Title, Tooltip, Legend, ArcElement, LineElement,LinearScale } from 'chart.js'
ChartJS.register(Title, Tooltip, Legend, ArcElement, LineElement, LinearScale)

const PieChartOptions = {
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      // display: false,
      position: 'right',

      onHover: (e, legendItem, legend) => {
        // console.log(e)
        // console.log(legendItem)
        console.log(legend)
        const index = legendItem.datasetIndex;
        const ci = legend.chart;
        // if(!ci.Tooltip.active){
        //   ci.Tooltip.active = true;
        // }
        // // if(ci.)
        // legend.active = true;
        console.log(`hovering on ${legendItem.text}`)
      }
    },
  },
  tooltips: {
    callbacks: {
      label: function (tooltipItem, data) {
        var dataset = data.datasets[tooltipItem.datasetIndex];
        var currentValue = dataset.data[tooltipItem.index];
        return dataset.labels[tooltipItem.index] + ":" + currentValue + " people"
      }
    }
  }
}


const PieChartData = {
  labels: ["Jail", "Parole", "State Prison", "Probation", "Federal Prison"],
  datasets: [{
    backgroundColor: ['#FFC329', '#A4E51B', '#E23110', '#FF7A1A', '#FF0000'],
    data: [1600, 2000, 2100, 3600, 420]
  },]
}

const PieChartStyle = {
  offset: "10px",
  weight: "10"
}

const LineChartData = {
  labels: ['1980', "1985", "1990", "1995", "2000", "2005", "2010", "2015", "2020"],
  datasets: [
    {
      label: 'New Hampshire Prison Incarceration Rates',
      backgroundColor: '#f87979', //#'FF0000'
      data: [450, 730, 1260, 2110, 2340, 2460, 2745, 2745, 2300]
    }
  ]
}

const LineChartOptions = {
  responsive: true,
  maintainAspectRatio: false,
  scales: {
    x: {
      type: 'category', // Register the 'category' scale for the x-axis
    },
    y: {
      beginAtZero: true,
      ticks: {
        stepSize: 1000,
      },
    },
  },
}

</script>

<template>
  <header>
    <h1>Vue Charts demo</h1>
  </header>

  <main>
    <div>
      <div class="chart-container" style="width: 50%; height: 100%;">
        <Pie :data="PieChartData" :options="PieChartOptions" :style="PieChartStyle" />
      </div>
      <div class="chart-container" style="width: 50%; height: 100%;">
        <Line :data="LineChartData" :options="LineChartOptions" />
      </div>
    </div>
  </main>
</template>

<style scoped>
.chart-container {
  background-color: #f0f0f0;
  border-radius: 10px;
  border: solid black 0.5px;
  padding: 10px
}
</style>
