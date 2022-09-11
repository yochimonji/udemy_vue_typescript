<script setup lang="ts">
const itemName1 = 'Desk'
const itemName2 = 'Bike'

const price1 = 40000
const price2 = 20000

const url1 = 'https://www.google.com'
</script>

<template>
  <div class="items-center flex-col flex">
    <h1>最近の支出</h1>
    <div class="justify-between h-20 w-96 flex items-center bg-blue-200 p-2">
      <label>{{ itemName1 }}</label>
      <label>{{ price1 }}円</label>
      <a :href="url1">Google</a>
    </div>
    <div class="justify-between h-20 w-96 flex items-center bg-blue-200 p-2">
      <label>{{ itemName2 }}</label>
      <label>{{ price2 }}円</label>
    </div>
  </div>
</template>
