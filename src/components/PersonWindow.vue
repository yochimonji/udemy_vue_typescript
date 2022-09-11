<script setup lang="ts">
    import { Ref, ref } from "vue";
    import PersonPostForm from "./PersonPostForm.vue"
    import PersonList from "./PersonList.vue"

    export type Person = {
        id: number,
        name: string,
        age: number
    }

    const persons: Ref<Person[]> = ref([{id: 0, name: "John", age: 24}, {id: 1, name: "Mike", age: 10}])

    const registerPerson = (person: Person) => {
        persons.value.push(person)
    }

    const deletePerson = (id: number) => {
        persons.value = persons.value.filter(person => person.id !== id)
    }
</script>

<template>
  <div class="flex flex-col items-center">
    <h1>Title</h1>
    <PersonPostForm @register="registerPerson" />
    <div class="flex flex-row justify-between w-4/5">
      <ul class="w-full">
        <PersonList
          :persons="persons"
          @delete="deletePerson"
        />
      </ul>
    </div>
  </div>
</template>