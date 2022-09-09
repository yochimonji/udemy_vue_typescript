<template>
    <div>
        <ul>
            <li v-for="todo in todos">
                {{ todo.title }}
            </li>
        </ul>
        <button @click="addTodo('add!')">Add</button>
    </div>
</template>

<script setup lang="ts">
import { inject } from 'vue';
import { Todo, todoKey } from "../useTodo"

// const todos = inject("todos")
// const _addTodo = inject("addTodo")
// const { todos, addTodo: _addTodo} = inject("todos")
const state = inject(todoKey)
if (!state) {
    throw new Error("state is undefined")
}
const { todos, addTodo: _addTodo } = state

const addTodo = (title: string) => {
    _addTodo(title)
}
</script>