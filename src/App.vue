<template>
  <div id="app">
    <TaskProgress :progress="progress" />
    <AddTask @taskAdded="addTask" />
    <TasksList @taskDeleted="deleteTask" :tasks="tasks" />
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
      tasks: [],
    };
  },
  components: {
    TaskProgress,
    AddTask,
    TasksList,
  },
  watch: {
    tasks: {
      deep: true,
      handler() {
        localStorage.setItem("tasks", JSON.stringify(this.tasks));
      },
    },
  },
  methods: {
    addTask(task) {
      const sameName = (t) => t.name === task.name;
      const reallyNew = this.tasks.filter(sameName).length === 0;
      if (reallyNew) {
        this.tasks.push({
          name: task.name,
          completed: false,
        });
      }
    },
    deleteTask(i) {
      this.tasks.splice(i, 1);
    },
  },
  computed: {
    progress() {
      const tasksTotal = this.tasks.length;
      const completed = this.tasks.filter((t) => t.completed).length;

      return Math.round((completed / tasksTotal) * 100) || 0;
    },
  },
  created() {
    const jsonTask = localStorage.getItem("tasks");
    this.tasks = JSON.parse(jsonTask) || [];
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
