<template>
  <div>
    <canvas id="myChart"></canvas>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import Chart from 'chart.js/auto';
import jsonData from './data.json'; 

  export default {
  name: 'App',
  setup() {
    const chart = ref(null);

    const createChart = (data) => {
      const ctx = document.getElementById('myChart').getContext('2d');
      chart.value = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: data.labels,
          datasets: data.datasets.map((dataset) => ({
            label: dataset.label,
            backgroundColor: dataset.backgroundColor,
            borderColor: dataset.borderColor,
            borderWidth: dataset.borderWidth,
            data: dataset.data,
          })),
        },
        options: {
          scales: {
            y: {
              beginAtZero: true,
            },
          },
        },
      });
    };

    onMounted(() => {
      createChart(jsonData);
    });

    return { chart };
  },
};
</script>
</script>
