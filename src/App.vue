<template>
  <div id="app">
    <h1>Todo Application</h1>
    <TodoList 
      v-bind:todos="todos"
      @remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {'id': 1, 'title': 'buy 1', 'completed': false},
        {'id': 2, 'title': 'buy 2', 'completed': false},
        {'id': 3, 'title': 'buy 3', 'completed': false},
      ]
    }
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  },
  components: {
    TodoList
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
