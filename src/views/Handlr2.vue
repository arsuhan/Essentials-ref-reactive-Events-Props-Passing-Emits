<template>
    <div class="bg-gray-500 p-3 text-base w-full">
        component-1
        <p>{{ inputProps }}</p>
        <button class="bg-red-400 p-4" @click="$emit('clearEmit')">clear</button>
    </div>
</template>

<script setup>

const props = defineProps(['inputProps'])
const emits = defineEmits(['clearEmit'])
</script>