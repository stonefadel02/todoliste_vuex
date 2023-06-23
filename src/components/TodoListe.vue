<template>

    <div> 
      <center>
       <table>
    
        <tr>
          <div v-for="todo in allTodos" :key="todo.id">
                <TodoTem :todo="todo" />
           </div>
        </tr>

    </table>
    </center>
    </div>
    
</template>

<script>
import TodoTem from './TodoTem.vue';
import { mapGetters } from "vuex";
export default {
    components: { TodoTem },
    computed: {
        ...mapGetters(["allTodos"])
    }
};
</script>


<style>
   table{
    margin-top: 20px;
   }
</style>
