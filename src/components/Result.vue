<template>
  <div id="result-container">
    <div class="result-title">
      <div class="sub-title">M Y&nbsp;&nbsp; R E S U L T</div>
      <div class="main-title">나의 결과는?</div>
    </div>
    <div v-for="(score, idx) in user" :key="idx" class="graph-container">
      <div class="ratio">
        <span class="score">{{ score }}</span>
        /
        <span class="total">10</span>
      </div>
      <div class="tendency left">{{ tendencies[idx][0] }}</div>
      <div class="chart-wrapper">
        <BarChart />
      </div>
      <div class="tendency right">{{ tendencies[idx][1] }}</div>
      <div class="ratio">
        <span class="score">2</span>
        /
        <span class="total">10</span>
      </div>
    </div>
  </div>
</template>

<script>
import referenceData from '../ReferenceData';
import BarChart from '../components/BarChart.vue';

const tendencies = [
  ['적극성', '수동성'],
  ['자신감', '신중함'],
  ['책임감', '무심함'],
  ['개인성향', '조직성향'],
  ['수평사고', '위계사고'],
];
console.log(referenceData);
export default {
  name: 'App',
  data() {
    return {
      user: referenceData.user,
      samsung: referenceData.samsung,
      kakao: referenceData.kakao,
      lg: referenceData.lg,
      tendencies: tendencies,
    };
  },
  methods: {},
  components: { BarChart },
};
</script>

<style>
* {
  box-sizing: border-box;
}
#result-container {
  width: 360px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.result-title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 118px;
  background-color: #fff;
}
/* @font-face {
  font-family: Agenor;
  src: url('../assets/font/Agenor-Regular/Agenor-Regular.ttf');
} */
.sub-title {
  font-family: Agenor;
  font-size: 12px;
  line-height: 16.8px;
  font-weight: 700;
}
.main-title {
  font-family: Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue',
    sans-serif;
  font-size: 36px;
  line-height: 50.4px;
  font-weight: 700;
}
.result-graph {
  width: 339px;
  height: 202px;
  background-color: rgba(0, 0, 0, 0.199);
}
.graph-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 12px;
  width: 310px;
  height: 40px;
}
.ratio {
  text-align: center;
  width: 37px;
  font-weight: 700;
}
.tendency {
  width: 55px;
  padding: 0 1px;
}
.tendency.left {
  text-align: right;
}
.tendency.right {
  text-align: left;
}
.chart-wrapper {
  margin-top: 8px;
  overflow: hidden;
  height: 30px;
}
</style>
