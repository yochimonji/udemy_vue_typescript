<script setup lang="ts">
import { ref } from "vue"

const tweets = ref([{id: 0, description: "Hello, world!"}, {id: 1, description: "This is the second tweet."}])
const inputtingDescription = ref<string>("")

const postTweet = () => {
    const tweet = {id: Math.random(), description: inputtingDescription.value}
    tweets.value.push(tweet)
    inputtingDescription.value = ""
    console.log("post...", inputtingDescription.value)
}

const deleteTweet = (id: number) => {
    tweets.value = tweets.value.filter(t => t.id !== id)
}
</script>

<template>
    <div class="flex flex-col items-center">
        <h1>Tweeter</h1>
        <div class="flex flex-col items-center p-4 bg-blue-100">
            <input type="text" class="border" v-model="inputtingDescription">
            <button class="bg-green-300 p-2 m-4 rounded-md shadow" v-on:click="postTweet">post</button>
        </div>
        <div class="flex flex-col items-center p-4">
            <p v-show="tweets.length <= 0">No tweets have been added</p>
            <ul>
                <li v-for="tweet in tweets" v-bind:key="tweet.id" class="list-none mb-3 rounded flex justify-between bg-sky-200 p-2 w-72">
                    <span>{{ tweet.description }}</span>
                    <button class="bg-red-400 hover:bg-red-600 p-2 m-4 rounded shadow" @click="deleteTweet(tweet.id)">delete</button>
                </li>
            </ul>
        </div>
    </div>
</template>