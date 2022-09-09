<script setup lang="ts">
import Card from './Card.vue';
import RocketIcon from './RocketIcon.vue';
</script>

<template>
    <div class="flex flex-col items-center">
        <Card title="Title">
            <div class="flex items-center">
                ここにさまざまなコンテンツが入ります
                <RocketIcon />
            </div>
        </Card>
        <Card title="Title">
            <div class="flex items-center">
                <RocketIcon />
                <RocketIcon />
                <RocketIcon />
            </div>
            <template #footer>
                <span>This is Footer</span>
                <RocketIcon size="12px" />
            </template>
        </Card>
        <Card title="Title">
            <div class="flex items-center">
                <RocketIcon />
                Rocket
                <RocketIcon />
            </div>
        </Card>
    </div>
</template>