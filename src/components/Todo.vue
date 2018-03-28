<template>
    <div>
        <!--v-for is kind of like *ngFor link: https://vuejs.org/v2/guide/list.html-->
        <div class='card-body' v-show="!isEditing">
            <div class='card-title'>
            {{ todo.title }}
            </div>
            <div class='card-text card-description'>
            {{ todo.description }}
            </div>
            <div class='card-text'>
            <span class='right floated edit icon' v-on:click="enableEdit">
                <i class='edit icon'></i>
            </span>
            <span class='right floated trash icon' v-on:click="deleteTodo(todo)">
                <i class='trash icon'></i>
            </span>
            </div>
        </div>
        <div class="content" v-show="isEditing">
            <div class="field">
                <label>Title</label>
                <input type="text" name="title" id="title" v-model="todo.title">
                <!--  here v-model is like ngModel  -->
            </div>
            <div class="field">
                <label>Description</label>
                <textarea name="description" id="description" cols="30" rows="3" v-model="todo.description"></textarea>
                <!--  here v-model is like ngModel  -->
            </div>
            <button class="btn btn-primary" v-on:click="disableEdit">
                <i class="close icon"></i>
            </button>
        </div>
        <!--v-show is kind of like *ngIf link: https://vuejs.org/v2/guide/conditional.html-->
        <div class='card-text ui green button mx-auto' v-show="!isEditing &&todo.done" disabled>
            Completed
        </div>
        <div class='card-text ui red button mx-auto' v-on:click="completeTodo(todo)" v-show="!isEditing && !todo.done">
            Complete
        </div>
    </div>
</template>

<script type="text/javascript">
  export default {
    props: ['todo'],
    data() {
        return {
            isEditing: false,
        };
    },
    methods: {
        completeTodo(todo) {
            this.$emit('complete-todo', todo);
        },
        deleteTodo(todo) {
            this.$emit('delete-todo', todo);
        },
        disableEdit() {
            this.isEditing = false;
        },
        enableEdit() {
            this.isEditing = true;
        }
    }
  };
</script>
<style scoped>
    label {
        display: block;
    }
    #description {
        width: 90%
    }
    input, textarea {
        margin-bottom: 10px;
    }
    input {
        text-align: center;
    }
    .icon {
        cursor: pointer;
    }
    .card-description {
        text-align: justify;
    }
</style>
