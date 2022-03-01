<template>
  <div id="container">
    <div class="result-title">
      <div class="sub-title">MY RESULT</div>
      <div class="main-title">나의 결과는?</div>
    </div>
    <div class="graph-container"></div>
    <BarChart />
  </div>
</template>

<script>
import referenceData from '../ReferenceData';
import BarChart from '../components/BarChart.vue';

const tendencys = [
  ['적극성', '수동성'],
  ['자신감', '신중함'],
  ['책임감', '무심함'],
  ['개인성향', '조직성향'],
  ['수평사고', '위계사고'],
];

export default {
  name: 'App',
  data() {
    return {
      user: referenceData.user,
      samsung: referenceData.samsungElectronics,
      kakao: referenceData.kakao,
      lg: referenceData.lgCNS,
      tendencys: tendencys,
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
  width: 50px;
}
</style>
