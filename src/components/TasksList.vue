<template>
  <div class="task-list">
    <template v-if="tasks.length">
      <Task
        v-for="(task, index) in tasks"
        :key="index"
        :task="task"
        @taskDeleted="$emit('taskDeleted', i)"
      />
    </template>
    <p v-else class="no-task">Começe a se organizar agora!!</p>
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

.no-task {
  margin: 0 auto;
  color: #aaa;
  font-size: 2rem;
}
</style>