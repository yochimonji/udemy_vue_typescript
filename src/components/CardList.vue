<script setup lang="ts">
import CardItem from './CardItem.vue'
import RocketIcon from './RocketIcon.vue'
</script>

<template>
  <div class="flex flex-col items-center">
    <CardItem title="Title">
      <div class="flex items-center">
        ここにさまざまなコンテンツが入ります
        <RocketIcon />
      </div>
    </CardItem>
    <CardItem title="Title">
      <div class="flex items-center">
        <RocketIcon />
        <RocketIcon />
        <RocketIcon />
      </div>
      <template #footer>
        <span>This is Footer</span>
        <RocketIcon size="12px" />
      </template>
    </CardItem>
    <CardItem title="Title">
      <div class="flex items-center">
        <RocketIcon />
        Rocket
        <RocketIcon />
      </div>
    </CardItem>
  </div>
</template>
