<template>
  <div id="container">
    <NavBar />
    <Search />
    <MessageBox />
    <PantagonChart />
    <div class="graph">graph</div>
    <div class="tabContainer">
      <CategoryTab
        :tabs="tabs"
        :currentTab="currentTab"
        @changeCurrentTab="changeCurrentTab"
      />
    </div>
    <Result />
  </div>
</template>
<script>
import referenceData from '../ReferenceData';
import Result from '../components/Result.vue';
import CategoryTab from '../components/CategoryTab.vue';
import PantagonChart from '../components/PantagonChart.vue';
import Search from '../components/Search.vue';
import MessageBox from '../components/MessageBox.vue';
import NavBar from '../components/NavBar.vue';

export default {
  name: 'App',

  data() {
    return {
      user: referenceData.user,
      samsung: referenceData.samsungElectronics,
      kakao: referenceData.kakao,
      lg: referenceData.lgCNS,
      currentTab: 0,
      tabs: [
        {
          name: '모두',
          icon: {
            src: require('../assets/select1.png'),
            alt: 'companyMe',
          },
        },
        {
          name: '본인',
          icon: {
            src: require('../assets/select2.png'),
            alt: 'Me',
          },
        },
        {
          name: '회사',
          icon: {
            src: require('../assets/select3.png'),
            alt: 'company',
          },
        },
      ],
    };
  },

  methods: {
    changeCurrentTab(i) {
      this.currentTab = i;
      console.log(i);
    },
  },

  components: { Search, MessageBox, PantagonChart, Result, CategoryTab, NavBar },
};
</script>

<style>
* {
  box-sizing: border-box;
}
#container {
  width: 360px;
  margin: 0 auto;
  /* background-color: rgba(255, 192, 203, 0.249); */
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

.tabContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 360px;
  height: 84px;
  top: 381px;
  padding: 20px, 16px, 20px, 16px;
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
