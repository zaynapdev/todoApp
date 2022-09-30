<template>
  <li class="task">{{ task }}</li>
</template>

<script>
export default {
  name: 'TaskLi',
  props: {
    task: String
  }
}
</script>

<style>
</style>