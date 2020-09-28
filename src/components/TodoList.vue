<template>
  <ul>
    <TodoItem 
      v-for="todo of todos" :key="todo.id"
      v-bind:todo="todo"
    />
  </ul>
</template>

<script>
import TodoItem from './TodoItem';

export default {
  props: ['todos'],
  components: {
    TodoItem
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>
