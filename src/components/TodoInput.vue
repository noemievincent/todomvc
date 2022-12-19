<template>
  <input class="new-todo" autofocus autocomplete="off" placeholder="What needs to be done?" v-model="inputText"
         @keyup.enter="createTodo()">
</template>
<script>
let id = 0;
export default {
  data() {
    return {
      inputText: ''
    };
  },
  emits: ['newTodo'],
  methods: {
    createTodo() {
      let newTodo = {id: id++, title: this.inputText, done: false};
      this.$emit('newTodo', newTodo);
      this.inputText = '';
    },
  },
  watch: {},
  name: "TodoInput"
};
</script>