<template>
<div>
    <!--JavaScript expressions in Vue are enclosed in double curly brackets.-->
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <div class='card todo-card' v-for="todo in todos">
      <div class='card-body'>
        <div class='card-title'>
          {{ todo.title }}
        </div>
        <div class='card-text'>
          {{ todo.project }}
        </div>
        <div class='card-text'>
          <span class='right floated edit icon'>
            <i class='edit icon'></i>
          </span>
        </div>
      </div>
      <div class='card-text ui bottom attached green basic button mx-auto' v-show="todo.done">
        Completed
      </div>
      <div class='card-text ui bottom attached red basic button mx-auto' v-show="!todo.done">
        Complete
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */ 
export default {
  name: 'TodoList',
  //we declare properties to accept the data sent from other components
  props: ['todos'],
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
