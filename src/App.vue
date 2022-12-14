<template>
  <div id="app">
    <input-block @addTask="tasks.push($event)" />

    <button class="remove-all-tasks" @click="removeAllTasks">
      Clear all tasks
    </button>

    <tasks-block
      :tasks="tasks"
      @removeTask="tasks.splice($event, 1)"
      @removedAllTasks="tasks = []"
    />
  </div>
</template>

<script>
import InputBlock from "./components/InputBlock.vue";
import TasksBlock from "./components/TasksBlock.vue";

export default {
  name: "App",
  data() {
    return {
      tasks: [],
    };
  },

  methods: {
    removeAllTasks: function () {
      this.tasks = [];
    },
  },

  components: {
    InputBlock,
    TasksBlock,
  },
};
</script>


<style>
#app {
  font-family: monospace;
  font-size: 20px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 0 15px;
}

.remove-all-tasks {
  display: block;
  margin: 0 auto;
  margin-top: 20px;
  width: 30%;
  min-width: 200px;
  height: 30px;
  border-radius: 25px;
  border: 1px solid #fff;
  background-color: rgb(64, 86, 138);
  color: #fff;
  cursor: pointer;
}
</style>