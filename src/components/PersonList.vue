<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'
import { Person } from './PersonWindow.vue'

type Props = {
  persons: Person[]
}

defineProps<Props>()

const emit = defineEmits(['delete'])
const onClickDelete = (id: number, name: string) => {
  if (confirm('Delete ' + name + '?')) {
    emit('delete', id)
  }
}
</script>

<template>
  <li
    v-for="person in persons"
    :key="person.id"
    class="flex justify-between items-center rounded bg-yellow-200 w-full m-2 p-2"
  >
    <span>{{ person.name }}</span>
    <span>age:{{ person.age }}</span>
    <button
      class="bg-gray-100 border rounded p-2"
      @click="onClickDelete(person.id, person.name)"
    >
      <span>delete</span>
    </button>
  </li>
</template>
