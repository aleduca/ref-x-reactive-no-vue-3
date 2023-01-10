<script setup>

import {ref, reactive} from 'vue';

const todos = reactive([]);
const todo = $ref('');

function addTask(){
  todos.push({name:todo});
  todo = '';
  console.log(todos);
}

</script>

<template>

<form @submit.prevent="addTask">
  <input type="text" v-model="todo">
  <button type="submit">Add task</button>
</form>

<h2>Todos</h2>

<ul>
  <li v-for="task in todos">
    {{ task.name }}
  </li>
  <li v-if="!todos.length">Add one or more tasks</li>
</ul>

</template>
