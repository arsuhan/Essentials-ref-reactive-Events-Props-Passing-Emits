<script setup>
const props = defineProps(['propsNumber'])
const emits = defineEmits(['plusEmit', 'mainusEmit'])

const plusComponent = () => {
    console.log('plusComponent');
    emits('plusEmit')
}

const mainusComponent = () => {
    console.log('mainusComponent');
    emits('mainusEmit')
}

</script>

<template>
    <div class="bg-red-400 p-3 text-base w-full">
        component-1 A
        <div class="flex justify-center">
      <button
        type="text"
        placeholder="anyhting text"
        class="border bg-amber-300 rounded-3xl p-2 mx-3"
        @click="plusComponent"
      >
        +
      </button>
      <p class="p-2 bg-amber-950 text-white">{{ propsNumber }}</p>
      <button
        type="text"
        placeholder="anyhting text"
        class="border bg-amber-500 rounded-3xl p-2 mx-3"
        @click="mainusComponent"
      >
        -
      </button>
    </div>
    </div>
    
</template>