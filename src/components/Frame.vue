<script setup lang="ts"></script>
<template>
  <div class="frame">
    <slot></slot>
  </div>
</template>
<style scoped>
.frame {
  padding: 16px 16px 16px 60px;
  width: 35rem;
  font-size: 1.5rem;
  font-style: italic;
  font-weight: 200;
  border: none;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  height: 65px;
  border: none;
  background: rgba(0, 0, 0, 0.003);
}
</style>
