<template>
  <div class="task-card" :class="task.completed ? 'done' : '' ">
    <span @click="$emit('taskDeleted', task)" class="close">x</span>
    <span @click="task.completed = !task.completed">{{task.name}}</span>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: ["task"],
  data() {
    return {
      completed: false,
    };
  },
};
</script>

<style scoped>
.task-card {
  position: relative;
  background-color: #4e3;
  padding: 20px 30px;
  margin: 15px;
  border: 1px solid #4e6;
  border-radius: 3px;
  font-size: 1.5rem;
  color: white;
  max-width: 200px;
  cursor: pointer;
  user-select: none;
}

.task-card:hover {
  transition: all 0.2s;
  box-shadow: 2px 4px 4px rgba(0, 0, 0, 0.3);
}

.done {
  background-color: #e53;
  border: 1px solid black;
  text-decoration: line-through;
}

.close {
  position: absolute;
  right: 8px;
  top: 5px;
  font-size: 0.8rem;
}
</style>