<template>
  <div>
    <h1>Tarefas</h1>
    <span class="progress">{{progress}} {{done}}</span>
  </div>
</template>

<script>
export default {
  name: "TaskProgress",
  data() {
    return {
      done: 0,
      inprogress: 0,
    };
  },
  computed: {
    progress() {
      if (this.done == 0 || this.inprogress == 0) {
        return "0 %";
      }
      return this.done / this.inprogress + "%";
    },
  },
};
</script>

<style scoped>
h1 {
  color: white;
}

.progress {
  display: block;
  width: 80%;
  margin: 0 auto;
  border: 2px solid white;
  border-radius: 2px;
  padding: 10px 0;
}
</style>