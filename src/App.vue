<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!--  <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <h1>Todo list</h1>
  <input style="cursor: pointer" v-model=message />
  <button v-on:click="addTask(tasks)">Добавити таск</button>
  <p v-for="(task, index) in tasks" v-bind:key="index">
    <task :task="task" @remove="removeTask(index)" />
  </p>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Task from './components/task.vue'

export default {
  name: 'App',
  components: {
    Task
  }, data() {
    return {
      message: 'Вивчити Vue.js!',
      tasks: ["asd", 'asd', 'asd'],
    }
  },
  methods: {
    addTask: function () {
      if (this.message) {
        this.tasks.push(this.message)
        this.message = ''
        console.log(this.tasks)
      }
    },
    removeTask: function (index) {
      delete this.tasks[index];
    },

  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
