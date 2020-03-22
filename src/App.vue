<template>
  <div id="app">
    <Todos />
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
          completed: true
        },
        {
          id: 3,
          title: "Brush teeth",
          completed: false
        }
      ]
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
