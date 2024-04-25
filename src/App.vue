<template>
  <div>
    <canvas id="myChart"></canvas>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import Chart from 'chart.js/auto';
import jsonData from './data.json'; 
</script>
