<template>
  <ul class="todo-list">
    <li class="todo" v-for="todo in todos" :key="todo.id" :class="{completed: todo.done}">
      <div class="view">
        <input class="toggle" type="checkbox" @change="toggleTodo(todo.id)" v-model="todo.done">
        <label>{{ todo.title}}</label>
        <button class="destroy"></button>
      </div>
      <input class="edit" type="text">
    </li>
  </ul>
</template>
<script>
export default {
  props: {
    'todos': Array
  },
  methods: {
    toggleTodo(id) {
      console.log(id);
      let todo = this.todos.filter((todo) => id === todo.id)[0];
      todo.done = !todo.done;
    },
  },
  name: 'todo-list'
};
</script>