<script setup lang="ts">
import { ref } from 'vue'

const { todos } = defineProps({
  todos: []
})

const inputValue = ref('')

const addTodo = (e: any) => {
  if (e.key === 'Enter') {
    // todos?.push(inputValue.value)
    inputValue.value = ''
  }
}
</script>
<template>
  <input @keydown="addTodo" v-model="inputValue" type="text" placeholder="What needs to be done?" />
</template>
<style scoped>
input {
  padding: 16px 16px 16px 60px;
  width: 35rem;
  font-size: 1.5rem;
  font-style: italic;
  font-weight: 300;
  border: none;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  height: 65px;
  border: none;
  background-color: #fff;
  z-index: 1;
}

input::placeholder {
  color: rgba(0, 0, 0, 0.5);
  font-weight: 400;
}

input:focus {
  box-shadow: 0 0 2px 2px #cf7d7d;
  outline: 0;
}
</style>
