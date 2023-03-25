<script setup>
import { ref } from 'vue'
import { useTodoListStore } from '../stores/todoList';

const store = useTodoListStore();

function addItemAndClear(item) {
  if (item.length === 0) {
    return
  }
  store.addTodo(item);
  todo.value = ''
}

const todo = ref('')
</script>

<template>
  <form @submit.prevent="addItemAndClear">
    <input v-model="todo" type="text" /><button>Add</button>
  </form>
</template>

<style>
</style>