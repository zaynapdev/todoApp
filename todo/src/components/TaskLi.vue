<template>
  <li class="task">
    <div class="checktask">
      <input class="check" type="checkbox" name="" :id="id">
      <label :for="id">
        {{ task }}
      </label>
    </div>
    <button @click="$emit('remove')" class="trash"></button>
  </li>
</template>

<script>
export default {
  name: 'TaskLi',
  props: {
    task: String,
    id: Number
  }
}
</script>

<style>
label{
  margin-left: 10px;
}
.check:checked + label{
  color: gray;
  border: none;
  text-decoration: line-through black;
}
.trash{
  border: none;
  background: none;
  width: 1.5rem;
  height: 1.5rem;
  background-image: url('../assets/trash.svg');
  background-size: cover;

}
.checktask{
  width: fit-content;
}
</style>