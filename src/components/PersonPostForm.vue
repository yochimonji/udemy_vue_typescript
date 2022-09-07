<script setup lang="ts">
    import { ref, defineEmits, computed } from 'vue';

    const inputtingName = ref<string>("")
    const inputtingAge = ref<number>(0)

    const emit = defineEmits(["register"])
    const register = () => {
        const person = { id: Math.random(), name: inputtingName.value, age: inputtingAge}
        emit("register", person)
    }

    const nameLengthLimit = 15
    const isValidName = computed(() => {
        if (inputtingName.value.length >= nameLengthLimit) {
            return false
        } else {
            return true
        }
    })
</script>

<template>
    <div class="flex flex-col items-center bg-gray-200 rounded w-96">
        <div class="flex flex-col justify-between w-4/5 m-4">
            <div class="flex justify-between pb-4">
                <span>name:</span>
                <input type="text" v-model="inputtingName" class="border rounded w-3/5" :class="isValidName ? 'bg-white' : 'bg-red-300'">
            </div>
            <span v-show="!isValidName" class="text-red-400">{{ nameLengthLimit }} characters or less, please</span>
            <div class="flex justify-between pb-4">
                <span>age:</span>
                <input type="number" v-model="inputtingAge" class="border rounded w-3/5">
            </div>
        </div>
        <button @click="register" :disabled="!isValidName" class="bg-white shadow-md rounded p-2 mb-4">register</button>
    </div>
</template>