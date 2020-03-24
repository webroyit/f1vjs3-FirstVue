<template>
  <div id="app">
    <Header />
    <!-- v-on to get the object from the AddTodo component -->
    <AddTodo v-on:add-todo="addTodo" />
    <!-- v-bind to pass data to another component -->
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo
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
    },
    // add a new item
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo];
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
