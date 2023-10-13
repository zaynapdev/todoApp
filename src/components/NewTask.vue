<template>
  <form  @submit.prevent="$emit('btn', text); text=''" class="newTask">
    <input class="input" v-model="text" type="text" placeholder="Введите текст">
    <button>Добавить</button>
  </form>
</template>

<script>
export default {
  name: 'NewTask',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    
  }
}

</script>

<style lang="scss">
.newTask{
  display: flex;
  gap: 20px;
  margin: auto;
  justify-content: center;
}
.input{
  width: 250px;
  padding: 13px;
}
</style>