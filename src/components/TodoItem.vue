<template>
  <li>
    <span v-bind:class="{'done': todo.completed}">
      <input type="checkbox" @change="todo.completed = !todo.completed">
      {{todo.title}}
    </span>
    <button type="submit" class="rm">X</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  }
}
</script>

<style scoped>
  li {
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
  }

  .rm {
    background: red;
    color: #fff;
    border-radius: 50%;
    font-weight: bold;
  }

  .done {
    text-decoration: line-through;
  }

  input {
    margin-right: 1rem;
  }
</style>