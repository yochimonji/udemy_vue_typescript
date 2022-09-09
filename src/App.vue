<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
// import Payment from "./components/Payment.vue"
// import Tweet from "./components/Tweet.vue"
// import Persons from './components/Persons.vue';
// import CardList from "./components/CardList.vue"
import TodoList from './components/TodoList.vue';
import { provide } from "vue"
import { todoKey, todos } from './useTodo';

// provide("todos", todos)
// provide("addTodo", addTodo)
provide(todoKey, todos)
</script>

<template>
  <div class="p-6 max-w-xl mx-auto">
    <!-- <Payment></Payment> -->
    <!-- <Tweet /> -->
    <!-- <Persons /> -->
    <!-- <CardList /> -->
    <TodoList />
  </div>
</template>
