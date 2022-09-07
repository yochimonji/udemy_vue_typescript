<script setup lang="ts">
import { ref, defineEmits } from 'vue';

const inputtingDescription = ref<string>("")

const emit = defineEmits(["post-tweet"])

const postTweet = () => {
    emit("post-tweet", inputtingDescription.value)
    inputtingDescription.value = ""
}

function add(a: number, b: number): number {
    return a + b
}
</script>

<template>
    <div class="flex flex-col items-center p-4 bg-blue-100">
        <input type="text" class="border" v-model="inputtingDescription">
        <button class="bg-green-300 p-2 m-4 rounded-md shadow" v-on:click="postTweet">post</button>
    </div>
</template>