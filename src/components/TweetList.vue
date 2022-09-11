<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';

type Tweet = {
    id: number,
    description: string
}
type Props = {
    tweets: Tweet[]
}

const emit = defineEmits(["delete-tweet"])
const deleteTweet = (id: number) => {
    emit("delete-tweet", id)
}

defineProps<Props>()
</script>

<template>
  <li
    v-for="tweet in tweets"
    :key="tweet.id"
    class="list-none mb-3 rounded flex justify-between bg-sky-200 p-2 w-72"
  >
    <span>{{ tweet.description }}</span>
    <button
      class="bg-red-400 hover:bg-red-600 p-2 m-4 rounded shadow"
      @click="deleteTweet(tweet.id)"
    >
      delete
    </button>
  </li>
</template>