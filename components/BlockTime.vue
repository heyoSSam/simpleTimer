<script lang="ts" setup>
import { defineProps } from 'vue';

let props = defineProps<{
        time: number,
        title: string
    }>()


</script>

<template>
    <div class="text-center border-solid border-2 p-5">
        <p class="text-3xl">{{ time }}</p>

        <p>{{ title }}</p>
    </div>
</template>

