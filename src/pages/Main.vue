<template>
  <div id="container">
    <div class="title flex-space-between">
      <h2>진단결과</h2>
      <span>다시 진단하기</span>
    </div>
    <div class="search-title flex-space-between">
      <span>검색 결과 ></span>
      <span>
        그레이비랩
        <button>x</button>
      </span>
    </div>
    <input placeholder="기업명을 검색하세요." />
    <div class="graph">graph</div>
    <div class="tabs">
      <button class="tab">모두</button>
      <button class="tab">본인</button>
      <button class="tab">회사</button>
    </div>
    <div class="result-title">
      <div class="sub-title">MY RESULT</div>
      <div class="main-title">나의 결과는?</div>
    </div>
    <div class="result-graph">result</div>
  </div>
</template>

<script>
import referenceData from '../ReferenceData';
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
.title {
  height: 72px;
}
.flex-space-between {
  width: 100%;
  padding: 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.search-title {
  height: 62px;
  padding: 20px 16px;
}

input {
  width: 328px;
  height: 48px;
  border-radius: 4px;
  border: none;
  background-color: #f8f8f8;
  margin-bottom: 20px;
}
input::placeholder {
  color: #b2b2b2;
}
.graph {
  background-color: rgba(128, 128, 128, 0.256);
  width: 100%;
  height: 381px;
}
.tabs {
  display: flex;
  width: 100%;
  padding: 14px 16px;
}
.tabs .tab {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
  padding: 14px 16px;
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
