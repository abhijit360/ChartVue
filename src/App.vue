<script setup lang="ts">
import {Bar, Pie} from "vue-chartjs"
import { Chart as ChartJS, Title, Tooltip, Legend,ArcElement  } from 'chart.js'
ChartJS.register(Title, Tooltip, Legend, ArcElement)

const chartOptions = {
        responsive: true,
        maintainAspectRation: false,
        plugins: {
          legend: {
            // display: false,
            position: 'bottom',

            onHover: (e,legendItem, legend)=>{
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

      }
      }

const chartData =  {
  labels: ["Jail", "Parole", "State Prison", "Probation", "Federal Prison"],
  datasets: [{
    backgroundColor: ['#FFC329', '#A4E51B','#E23110','#FF7A1A', '#FF0000'],
    data:[1600,2000,2100,3600,420]},]
}




</script>

<template>
  <header>
    <h1>Vue Charts demo</h1>
  </header>

  <main>
    <div style="width: 25%; height: 100%;">
        <Pie
            :data="chartData"
            :options="chartOptions"
        />
    </div>
  </main>
</template>

<style scoped>
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
