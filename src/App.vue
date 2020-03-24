<template>
  <div id="app">
    <!-- v-bind to pass data to another component -->
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos';

export default {
  name: 'App',
  components: {
    Todos
  },
  // store values
  data(){
    return{
      todos: [
        {
          id: 1,
          title: "Buy water",
          completed: false
        },
        {
          id: 2,
          title: "Clean disk",
          completed: false
        },
        {
          id: 3,
          title: "Brush teeth",
          completed: false
        }
      ]
    }
  },
  methods: {
    // remove an item
    deleteTodo(id){
      // filter to return anything based on the condition
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  } 
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
</style>
