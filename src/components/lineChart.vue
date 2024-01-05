<template>
    <div>
        <apexchart 
            width="500" 
            type="line" 
            stacked="false"
            :series="LineChartData" 
            :options="LineChartOptions"></apexchart>
    </div>
</template>
<script setup lang="ts">

    const LineChartData = [
    {
      name: "New Hampshire Prison Incarceration Rates",
      type:"line",
      data: [450, 730, 1260, 2110, 2340, 2460, 2745, 2745, 2300]
    }
  ]

    const LineChartOptions = {
        dataLabels: {
            enabled: true,
        },
  colors: ["#FF1654"],
  stroke: {
    curve :'smooth',
  },
  xaxis: {
    categories: [1980, 1985, 1990, 1995, 2000, 2005, 2010, 2015, 2020],
  },
  yaxis: [
    {
      axisTicks: {
        show: true
      },
      axisBorder: {
        show: true,
        color: "#FF1654"
      },
      labels: {
        style: {
          colors: "#FF1654"
        }
      },
      title: {
        text: "Incarceration Rates",
        style: {
          color: "#FF1654"
        }
      }
    },
  ],
  legend: {
    show: true,
    position: "top",
    horizontalAlign: "left",
    offsetX: 40
  }
}
</script>
