<script setup lang="ts">
    import { defineProps } from 'vue';

    defineProps<{
        title: string
    }>()
</script>

<template>
  <div class="flex flex-col items-center shadow rounded pt-4 mb-4 w-80 bg-gray-200">
    <div class="p-2">
      <span class="text-lg border">{{ title }}</span>
      <slot />
    </div>
    <div class="flex justify-center shadow rounded-b bg-blue-500 w-full p-2 m-0">
      <slot name="footer">
        Default Footer
      </slot>
    </div>
  </div>
</template>