<template>
  <BarChart
    @click="test"
    id="bar-chart"
    ref="doughnutRef"
    :chartData="testData"
    :options="options"
    :style="{
      width: '110px',
      height: '50px',
      alignItems: 'center',
      top: '5px',
    }"
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

  props: {
    userScore: Number,
    companyScore: Number,
  },
  data() {
    return {
      currentUserScore: this.userScore,
      currentCompanyScore: this.companyScore,
      matchData: 6,
    };
  },
  methods: {
    test() {
      console.log(this.userScore, this.companyScore, this.currentData);
    },
  },

  setup() {
    const data = ref([8, -3]);
    console.log('data', data.value);
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
          display: false,
          grid: {
            display: false,
          },
        },
        x: {
          display: false,
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
      labels: ['적극적인', '자신있는', '책임있는', '개인주의', '수평적인'],
      datasets: [
        {
          data: data.value,
          backgroundColor: ['#6e3cf9', '#ffd966'],
          barThickness: 5,
          bar: { backgroundColor: 'red' },
        },
      ],
    }));

    return { testData, doughnutRef, options };
  },
  beforeMount() {
    // this.testData.datasets.data

    this.testData.datasets[0].data[0] = this.userScore;
    this.testData.datasets[0].data[1] = this.companyScore;
  },
});
</script>

<style>
#bar-chart {
  display: block;
  width: 100px;
}
.check {
  position: fixed;
  width: 200px;
  z-index: 9;
}
</style>
