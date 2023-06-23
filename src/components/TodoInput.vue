<template>
      <h1>TodoListe</h1>
    <div>
        <center>
            <input @change="todoTextChange" v-bind:value="todoText" type="text">
            <button @click="addTodoI">Add</button>
        </center>
    </div>
</template>

<script>
import { mapActions } from "vuex";
import { v1 } from "uuid";

export default {
    data() {
        return {
            todoText: " "
        };
    },
    methods: {
        ...mapActions(["addTodo"]),
        todoTextChange(e) {
            this.todoText = e.target.value;
        },
        addTodoI() {
           this.addTodo({
            id: v1(),
            title: this.todoText
           });
           this.todoText = " ";
        }
    }
};
</script>
<style>
h1{
    text-align: center;
    font-size: 60px;
    color: blue;
}

button{
    color: white;
    background-color: blue;
    border: none;
    border-radius: 6px;
    width: 90px;
    height: 35px;
    font-size: 15px;
    margin-left: 20px;
}

input{
    border-radius: 6px;
    height: 35px;
    border-color: rgba(129, 90, 106, 0.288);
}

</style>