<template>
  <div id="app">
    <task
      v-for="(task, index) in tasks"
      :message="task.message"
      :key="index"
      :index="index"
      :ref="'task' + index"
    />
  </div>
</template>

<script>
import Task from "./components/Task.vue";
// import LeaderLine from "leader-line-vue";

export default {
  name: "App",
  components: { Task },
  data() {
    return {
      tasks: [
        { message: "hello" },
        { message: "hello" },
        { message: "hello" },
        { message: "hello" },
        { message: "hello" },
        { message: "hello" },
      ],
      line1: undefined,
    };
  },
  mounted() {
    new LeaderLine(
      document.querySelector("#task-0"),
      document.querySelector("#task-1")
    );
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: blue;
  height: 100vh;
  width: 100vw;
  display: flex;
}
</style>
