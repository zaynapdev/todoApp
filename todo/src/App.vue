<template>
  <div>
    <h1>Todo List</h1>
    <NewTask @btn="addTask"/>
    <Tasks :tasks="arr"/>
  </div>
</template>

<script>
import NewTask from './components/NewTask.vue'
import Tasks from './components/Tasks.vue'

export default {
  name: 'App',
  components: {
    NewTask,
    Tasks
  },
  data() {
    return {
      arr: JSON.parse(localStorage.getItem('arr')) ?? []
    }
  },
  methods: {
    addTask(task) {
      if (task != '') {
        this.arr.push(task)
        localStorage.setItem('arr', JSON.stringify(this.arr))
        console.log(this.arr)
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
