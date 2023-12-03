<script setup lang="ts">
import CloseIcon from './icons/CloseIcon.vue'
const { todo, todos } = defineProps({
  todo: String,
  todos: [String]
})

const deleteTodo = (e: any) => {
  // todos?.splice(todos.indexOf(e.target.innerHTML), 1)
}
</script>
<template>
  <div class="todo">
    <div class="circle"></div>
    <p>{{ todo }}</p>
    <CloseIcon @click="deleteTodo" class="close-icon" />
  </div>
</template>
<style scoped>
.todo {
  position: relative;
  padding: 16px 16px 16px 60px;
  /* width: 35rem; */
  font-size: 1.5rem;
  font-style: italic;
  font-weight: 200;
  border: none;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  height: 65px;
  background-color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: default;
}

.todo:hover > .close-icon {
  opacity: 1;
}

.close-icon {
  width: 1.5rem;
  height: 1.5rem;
  opacity: 0;
  cursor: pointer;
}

.circle {
  border: 1px solid black;
  position: absolute;
  width: 1.5rem;
  height: 1.5rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  top: 50%;
  left: 0;
  transform: translate(50%, -50%);
}
</style>
