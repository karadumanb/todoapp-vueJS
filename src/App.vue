<template>
  <div id="app">
    <h1>Todo App</h1>
    <todo-list v-bind:todos="todos"></todo-list>
  </div>
  
</template>

<script>
/* eslint-disable */ 
import TodoList from './components/TodoList'

export default {
  name: 'App',
  components: {
    TodoList
  },
  //data function is used to return data for template
  //if we want to use this in another component, we need to use v-bind in template
  data() {
    return {
      todos: [{
        title: 'Todo 1',
        description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut voluptates dolorem tempore!',
        done: false,
      }, {
        title: 'Todo 2',
        description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut voluptates dolorem tempore!',
        done: true,
      }, {
        title: 'Todo 3',
        description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut voluptates dolorem tempore!',
        done: false,
      }, {
        title: 'Todo 4',
        description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut voluptates dolorem tempore!',
        done: false,
      }],
    };
  }
}
</script>

<style>

</style>
