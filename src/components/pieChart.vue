<template>
    <div>
        <apexchart width="500" type="pie" :series="PieChartData" :options="PieChartOptions"></apexchart>
    </div>
</template>
<script setup lang="ts">
   
    const PieChartData =  [1600, 2000, 2100, 3600, 420]
    
    const PieChartOptions = {
        labels:  ["Jail", "Parole", "State Prison", "Probation", "Federal Prison"],
        dataLabels :{
            enabled: true,
            formatter: function (val, {seriesIndex, dataPointIndex, w}){
                console.log("value",val)
                console.log("seriesINdex",seriesIndex)
                console.log("datapointIndex:",dataPointIndex)
                console.log("w",w)
                return w.config.labels[seriesIndex] + ":" + Math.round(val *10)/10 + "%"
            }
        },
        colors: ['#FFC329', '#A4E51B', '#E23110', '#FF7A1A', '#FF0000'],
        plotOptions:{
            pie: {
               size:250,
               customScale: 0.8,
               expandOnClick: false
            },
        },
        animations:{
            enabled: true,
            easing: 'easeinout',
            speed: 800,
            animaateGradually:{
                enabled: true,
                delay: 150,
            },
            dynamicAnimation:{
                enabled: true,
                speed: 350
            }
        }
    };

</script>