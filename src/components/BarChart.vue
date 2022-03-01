<template>
  <BarChart :chartData="testData" />
</template>

<script>
// import { Chart, DoughnutController, ArcElement, Tooltip } from "chart.js";
import { Chart, registerables } from 'chart.js';
import { defineComponent } from 'vue';
import { BarChart } from 'vue-chart-3';
Chart.register(...registerables);

export default defineComponent({
  name: 'Home',
  components: { BarChart },
  setup() {
    const testData = {
      labels: ['Paris', 'Nîmes', 'Toulon', 'Perpignan', 'Autre'],
      datasets: [
        {
          data: [30, 40, 60, 70, 5],
          backgroundColor: [
            '#77CEFF',
            '#0079AF',
            '#123E6B',
            '#97B0C4',
            '#A5C8ED',
          ],
        },
      ],
    };

    return { testData };
  },
});
</script>
