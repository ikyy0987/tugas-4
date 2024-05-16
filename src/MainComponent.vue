<template>
  <div class="container">
    <div class="header">
      <h1>Menu</h1>
      <button @click="selectedMenu = 'Todos'" :class="{ active: selectedMenu === 'Todos' }">Todos</button>
      <button @click="selectedMenu = 'Post'" :class="{ active: selectedMenu === 'Post' }">Post</button>
    </div>
    <div class="content">
      <TodoApp v-if="selectedMenu === 'Todos'" />
      <PostApp v-else-if="selectedMenu === 'Post'" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import TodoApp from './components/TodoApp.vue';
import PostApp from './components/PostApp.vue';

const selectedMenu = ref('Todos');
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  background-color: #f0f0f0;
  min-height: 100vh;
}

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.header h1 {
  margin-right: 20px;
}

.header button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  margin: 0 5px;
  cursor: pointer;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.header button:hover {
  background-color: #0056b3;
}

.header button.active {
  background-color: #0056b3;
  font-weight: bold;
}

.content {
  display: flex;
  justify-content: center;
  width: 100%;
}

.todo-app, .post-app {
  width: 100%;
  max-width: 600px;
  background: white;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}
</style>




