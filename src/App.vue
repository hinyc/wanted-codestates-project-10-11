<template>
  <h1>wanted-codestates-project-10-11</h1>
  <Search />
  <MessageBox />
</template>

<script>
import Search from "./components/Search.vue";
import MessageBox from "./components/MessageBox.vue";

export default {
  name: "App",
  components: {
    Search,
    MessageBox,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
