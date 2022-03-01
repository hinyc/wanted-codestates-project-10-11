<template>
  <BarChart ref="doughnutRef" :chartData="testData" :options="options" />
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
    const data = ref([30, 40, 60, 70, 5]);
    const doughnutRef = ref();

    const options = ref({
      responsive: true,
      plugins: {
        legend: {
          position: 'top',
        },
      },
      indexAxis: 'y',
    });

    const testData = computed(() => ({
      labels: ['적극성', '자신감', '책임감', '개인성향', '수평사고'],
      datasets: [
        {
          data: data.value,
          backgroundColor: ['#6e3cf9'],
        },
      ],
    }));

    return { testData, doughnutRef, options };
  },
});
</script>
