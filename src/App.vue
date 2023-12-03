<script setup lang="ts">
import { ref, watch, watchEffect } from 'vue'
import HeaderVue from './components/Header.vue'
import TodoInput from './components/TodoInput.vue'
import Todo from './components/Todo.vue'

const STORAGE_KEY = 'vue-todomvc'

const todos = ref(JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]'))

// persist state
watchEffect(() => {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(todos.value))
})
</script>

<template>
  <main>
    <header>
      <HeaderVue />
      <div class="todo-main">
        <TodoInput :todos="todos" />
        <div v-for="(todo, i) in todos">
          <Todo :key="i" :todo="todo" :todos="todos" />
        </div>
      </div>
    </header>
  </main>
</template>

<style scoped>
main {
  background-color: #f5f5f5;
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
}

header {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  align-items: center;
  font-weight: 200;
}

.todo-main {
  display: flex;
  flex-direction: column;
}
</style>
