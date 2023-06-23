<template>
    <div>
        <center>
            <div class="item">
        <h3 v-if="!editing">{{ todo.title }}</h3>
        <input v-bind:value="todoText" @change="todoTextChange" v-else type="text">
        <div class="but">
        <button class="update" @click="toggleEditing">{{ editing ? 'Update' : 'Edit' }}</button>
        <button  class="delete" @click="deleteTodo(todo.id)">Delete</button>
        </div>
            </div>
        </center>
    </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
    props: {
        todo: {}
    },
    data() {
        return {
            todoText: '',
            editing: false,
        };
    },
    methods: {
        ...mapActions(["deleteTodo", "updateTodo"]),
        todoTextChange(e) {
            this.todoText = e.target.value;
        },
        toggleEditing() {
            this.editing = !this.editing;
            if (this.editing) {
                this.todoText = this.todo.title;
            } else {
                this.updateTodoTitle(this.todo);
            }
        },
        updateTodoTitle(todo) {
            todo.title = this.todoText;
            this.updateTodo(todo);
        }
    },
};
</script>

<style>
 .item{
    display: flex;
 }

 .delete{
    background-color: red;
    margin: 10px;

 }

 .update{
    background-color: green ;
    
 }

.but{
    margin-left: 10px;
    padding-right: 35px;
    justify-content: space-between;
}
</style>
