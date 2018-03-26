<template>
    <div>
        <!--v-for is kind of like *ngFor link: https://vuejs.org/v2/guide/list.html-->
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
        <!--v-show is kind of like *ngIf link: https://vuejs.org/v2/guide/conditional.html-->
        <div class='card-text ui green button mx-auto' v-show="todo.done">
            Completed
        </div>
        <div class='card-text ui red button mx-auto' v-show="!todo.done">
            Complete
        </div>
        </div>
    </div>
</template>

<script type="text/javascript">
  export default {
    props: ['todo'],
  };
</script>