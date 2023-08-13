<script setup>
import {ref, onMounted, onBeforeMount, onUnmounted, onUpdated, onBeforeUnmount } from 'vue';

let chart = null
const dataset = [
  300, 120, 151
]

const data = {
  labels: [
    'Red',
    'Blue',
    'Yellow'
  ],
  datasets: [{
    label: 'My First Dataset',
    data: dataset,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)'
    ],
    hoverOffset: 4
  }]
};

const config = {
  type: 'doughnut',
  data: data,
};

onMounted(()=> {
  const ctx = document.getElementById('myChart');
  chart = new Chart(ctx, config)
});

onBeforeUnmount(()=> {
  chart.destroy()
});



</script>

<template>
    <div>
  <canvas id="myChart"></canvas>
</div>
</template>

<style scoped>

</style>
