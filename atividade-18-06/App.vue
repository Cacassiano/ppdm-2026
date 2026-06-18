<script setup>
import { ref, computed } from 'vue'
import TaskList from './TaskList.vue';
const taskList = ref(["Tarefas importantes"])
const newList = ref("");
const handleSubmit = (e) => {
    e.preventDefault()
    taskList.value.push(newList.value);
    newList.value = "";
  }
</script>


<template>
  <form @submit="handleSubmit">
    <input v-model="newList" placeholder="crie uma nova lista de Tarefas" required/>
    <button>Create New list</button>
  </form>  
  <li v-for="list in taskList">
    <TaskList :title="list" />
  </li>
</template>
