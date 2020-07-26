<template>
  <div id="app">
    <TaskProgress />
    <AddTask />
    <TasksList :tasks="tasks" />
  </div>
</template>

<script>
import TaskProgress from "@/components/TaskProgress.vue";
import TasksList from "@/components/TasksList.vue";
import AddTask from "@/components/AddTask.vue";

export default {
  name: "App",
  data() {
    return {
      tasks: [
        { name: "Lavar louça", completed: false },
        { name: "Limpar sala", completed: true },
      ],
    };
  },
  components: {
    TaskProgress,
    AddTask,
    TasksList,
  },
  methods: {
    made() {},
  },
};
</script>

<style>
body {
  background-color: #2c3e50;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #2c3e50;
  margin-top: 60px;
}
</style>
