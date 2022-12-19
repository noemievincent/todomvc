<script>
import TodoInput from '@/components/TodoInput.vue';
import ToggleAll from "@/components/ToggleAll.vue";
import TodoList from "@/components/TodoList.vue";
import TodoCount from "@/components/TodoCount.vue";
import TodoFilters from "@/components/TodoFilters.vue";
import ClearCompleted from "@/components/ClearCompleted.vue";

export default {
  components: {
    ClearCompleted,
    TodoFilters,
    TodoCount,
    TodoList,
    ToggleAll,
    TodoInput,
  },
  data() {
    return {
      todos: [
        // {id: 0, title: "Quelque chose à faire", done: false}
      ],
    }
  }
};
</script>
<template>
  <header class="header">
    <h1>todos</h1>
    <todo-input @newTodo="(todo) => this.todos.push(todo)"/>
  </header>
  <section class="main">
    <toggle-all/>
    <todo-list :todos="todos"/>
  </section>
  <footer class="footer">
    <todo-count/>
    <todo-filters/>
    <clear-completed/>
  </footer>
</template>
