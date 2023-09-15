<script  setup>
import { ref } from 'vue'
const newTodoItem = ref('')
const todos = ref([
  {id:1,title:'title 1'},
  {id:2,title:'title 2'},
  {id:3,title:'title 3'}
])
let newTodoId = 4
function addTotoItems()
{
  todos.value.push({
    id:newTodoId++,
    title: newTodoItem.value
  })
}
console.log(todos.value)
function removeTodoItem(item)
{
  todos.value.splice(item, 1)
}
</script>

<template>
  <form @submit.prevent="addTotoItems">
    <input v-model="newTodoItem">
    <button>add</button>
  </form>
  <ul>
    <li v-for="(todo, index) in todos" :key="todo.id">
    {{ todo.title }}
    <button @click="removeTodoItem(index)">X</button>
    </li>
  </ul>
</template>

<style  scoped>
  
</style>
