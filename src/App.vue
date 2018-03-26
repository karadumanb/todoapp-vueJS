<template>
  <div id="app">
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
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  }
}
</script>

<style>

</style>
