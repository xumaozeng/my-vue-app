<template>
  <div id="app">
    <img src="./assets/logo.png" alt="Vue log" />
    <span class="title">开课吧</span>
    <course-list />
  </div>
</template>

<script>
import CourseList from "./components/CourseList.vue";

export default {
  name: "App",
  components: {
    CourseList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
}
img {
  width: 20px;
}
.title {
  vertical-align: super;
  margin-left: 10px;
}
</style>
