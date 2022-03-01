<template>
  <BarChart
    id="bar-chart"
    ref="doughnutRef"
    :chartData="testData"
    :options="options"
  />
</template>

<script>
import { Chart, registerables } from 'chart.js';
import { computed, defineComponent, ref } from 'vue';
import { BarChart } from 'vue-chart-3';
Chart.register(...registerables);

export default defineComponent({
  name: 'Home',
  components: { BarChart },
  setup() {
    const data = ref([-8, -10, -10, 3, -6]);
    const doughnutRef = ref();

    const options = ref({
      responsive: true,
      plugins: {
        legend: {
          position: 'top',
        },
      },
      indexAxis: 'y',
      scales: {
        y: {
          backgroundColor: 'black',
          grid: {
            display: false,
          },
        },
        x: {
          backgroundColor: 'red',
          grid: {
            display: false,
          },
          ticks: {
            display: true,
            stepSize: 2,
          },
          min: -10,
          max: 10,
        },
      },
    });

    const testData = computed(() => ({
      labels: ['적극성', '자신감', '책임감', '개인성향', '수평사고'],
      datasets: [
        {
          data: data.value,
          backgroundColor: ['#6e3cf9'],
          barThickness: 10,
        },
      ],
    }));

    return { testData, doughnutRef, options };
  },
});
</script>

<style>
#bar-chart {
  /* width: 100px;
  height: 200px; */
}
</style>
