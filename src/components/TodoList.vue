<template>
  <div>
    <!--JavaScript expressions in Vue are enclosed in double curly brackets.-->
    <!--With filter functions we calculated amount of tasks with done property-->
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <!--v-for is kind of like *ngFor link: https://vuejs.org/v2/guide/list.html-->
    <todo  v-for="todo in todos"></todo>
  </div>
</template>

<script>
/* eslint-disable */ 
import Todo from './Todo';
export default {
  //we declare properties to accept the data sent from other components
  props: ['todos'],
   components: {
    Todo,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .todo-card {
 width: 25%; 
 margin:10px;
 }
 .card {
  border: 2px solid skyblue;
  text-align: center;
 }
 .button {
   width: 50%;
   text-align: center;
 }
</style>
