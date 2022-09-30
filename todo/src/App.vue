<template>
  <div>
    <h1>Todo List</h1>
    <NewTask @btn="addTask"/>
    <div class="tasks">
      <ul>
        <TaskLi @remove="removeTask(task)" v-for="task in this.arr" :task="task.task" :key="task.id"/>
      </ul>
    </div>
  </div>
</template>

<script>
import NewTask from './components/NewTask.vue'
import TaskLi from './components/TaskLi.vue'

export default {
  name: 'App',
  components: {
    NewTask,
    TaskLi
  },
  data() {
    return {
      arr: JSON.parse(localStorage.getItem('arr')) ?? [],
      id: JSON.parse(localStorage.getItem('id')) ?? 0
    }
  },
  methods: {
    addTask(task) {
      if (task != '') {
        this.id++
        localStorage.setItem('id', JSON.stringify(this.id))
        this.arr.push({task: task, id: this.id})
        localStorage.setItem('arr', JSON.stringify(this.arr))
      }
    },
    removeTask(item) {
      let id = this.arr.indexOf(item)
      this.arr.splice(id, 1)
      localStorage.setItem('arr', JSON.stringify(this.arr))
      console.log(id)
      console.log(this.arr)
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
button{
  cursor: pointer;
}
.tasks{
  width: 900px;
  margin: auto;
}
ul{
  display: flex;
  flex-direction: column;
}
li{
  padding: .8rem;
  box-shadow: 0px 0px 2px gray;
  margin: .6rem 0 0;
  text-align: start;
  list-style: none;
  display: flex;
  justify-content: space-between;
}
</style>
