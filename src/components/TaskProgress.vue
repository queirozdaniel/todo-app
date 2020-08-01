<template>
  <div>
    <h1>Tarefas</h1>
    <div class="task-progress">
      <span class="progress-value">{{progress}}%</span>
      <div class="progress-bar" :style="{width: progress +'%'}"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TaskProgress",
  props: {
    progress: {
      type: Number,
      default: 0,
    },
  },
};
</script>

<style scoped>
h1 {
  color: white;
}

.task-progress {
  position: relative;
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 80%;
  margin: 0 auto;
  border: 2px solid white;
  border-radius: 5px;
  padding: 10px 0;
  color: white;
}

.progress-bar {
  position: absolute;
  top: 0;
  height: 100%;
  background-color: #44ee33;
  border-radius: 3px;
  align-self: flex-start;
}

.progress-value {
  z-index: 10;
}
</style>