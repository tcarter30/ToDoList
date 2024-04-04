<script setup>

import { ref } from 'vue';
//initializing id that will be used to increment ove the array
let id= 0
// creating a variable that will hold new todo items
const newTodo =(ref(''))
const todos = ref([
  {id: id++, text:'Learn HTML'},
  {id: id++, text: 'Learn Javascript'},
  {id: id++, text:'Learn Vue'}
])
function addTodo(){
  //incomplete function needs more to work
  newTodo.value = ''
}
function removeTodo(todo){
  //incomplete function needs more to work

}

</script>

<template>
  <form @submit.prevent="addTodo">
  <input v-model="newTodo" required placeholder="new todo"/>
  <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
     {{  todo.text }}
      <button @click="removeTodo(todo)">X</button>
      </li>
  </ul>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
