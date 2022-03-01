<template>
  <div id="container">
    <div class="result-title">
      <div class="sub-title">MY RESULT</div>
      <div class="main-title">나의 결과는?</div>
    </div>
    <BarChart />
  </div>
</template>

<script>
import referenceData from '../ReferenceData';
import BarChart from '../components/BarChart.vue';
export default {
  name: 'App',
  data() {
    return {
      user: referenceData.user,
      samsung: referenceData.samsungElectronics,
      kakao: referenceData.kakao,
      lg: referenceData.lgCNS,
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
#container {
  width: 360px;
  margin: 0 auto;
  background-color: rgba(255, 192, 203, 0.249);
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
.result-graph {
  width: 339px;
  height: 202px;
  background-color: rgba(0, 0, 0, 0.199);
}
</style>
