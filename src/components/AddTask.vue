<template>
  <div class="add-task">
    <input
      class="form-element"
      v-model="info"
      @keydown.enter="add"
      type="text"
      placeholder="Nova tarefa ?"
    />
    <button class="form-element" @click="add">+</button>
  </div>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      info: "",
    };
  },
  methods: {
    add() {
      this.$emit("taskAdded", { info: this.info });
      this.info = "";
    },
  },
};
</script>

<style scoped>
.add-task {
  margin: 35px;
}

.form-element {
  outline: none;
  font-size: 2rem;
  border: 1px solid #fff;
  padding: 5px 10px 8px;
  color: #fff;
}

input.form-element {
  width: 500px;
  background: #fff2;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 8px;
}

button.form-element {
  border-left: none;
  cursor: pointer;
  background-color: #2196f3;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
}
</style>