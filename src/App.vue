<script setup lang="ts">
  import pieChartVue from './components/pieChart.vue';
  import lineChart from './components/lineChart.vue';
</script>

<template>
  <header>
    <h1>Vue Charts demo</h1>
  </header>

  <main>
      <div style="display: flex; flex-direction: row; gap:100px">
          <div><pieChartVue /></div>
          <div><lineChart /></div>
      </div>
    </main>
</template>

