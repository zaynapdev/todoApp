<template>
  <div class="tasks">
    <ul>
      <TaskLi v-for="task in tasks" :task="task" :key="task"/>
    </ul>
  </div>
</template>

<script>
import TaskLi from './TaskLi.vue'

export default {
  name: 'Tasks',
  components: {
    TaskLi
  },
  props: {
    tasks: Array
  }
}
</script>

<style>
.tasks{
  width: 900px;
  display: flex;
  gap: 20px;
  margin: auto;
}
li{
  margin: 15px 0;
  text-align: start;
  border-bottom: 1px solid green;
  list-style: auto;
}

</style>