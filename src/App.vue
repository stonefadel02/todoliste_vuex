<template>
  
  <TodoInput />
   <TodoListe />
  <TodoTem />
 
</template>

<script>
import TodoListe from './components/TodoListe.vue'
import TodoInput from './components/TodoInput.vue'
import TodoTem from   './components/TodoTem.vue'

export default {
  name: 'App',
  components: {
    TodoListe,
    TodoInput,
    TodoTem,
  }
}
</script>

<style>
  
</style>
