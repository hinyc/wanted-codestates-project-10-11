<template>

  <h1>wanted-codestates-project-10-11</h1>
  <Search />
  <MessageBox />
    <Main />
</template>


<script>
import Search from "./components/Search.vue";
import MessageBox from "./components/MessageBox.vue";
import Main from './pages/Main.vue'
export default {
  name: "App",
  components: {
    Search,
    MessageBox,
    Main
  },

};
</script>

<style></style>
