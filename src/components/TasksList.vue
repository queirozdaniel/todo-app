<template>
  <div class="task-list">
    <Task v-for="(task, index) in tasks" :key="index" :info="task" />
  </div>
</template>

<script>
import Task from "@/components/Task.vue";

export default {
  name: "TasksList",
  components: {
    Task,
  },
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.task-list {
  display: flex;
}
</style>