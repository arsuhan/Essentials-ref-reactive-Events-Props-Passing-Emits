<!-- <template>
    <div class="bg-red-500 w-full">
        Components-1

        <div class="flex p-4 justify-center">
      <button @click="plusComponent" class="bg-green-500 p-2 text-3xl rounded-full mx-2">+</button>
      <p class="p-2 bg-amber-300 text-black">{{ numberProps }}</p>
      <button @click="mainusComponent" class="bg-green-500 p-2 text-3xl rounded-full mx-2">-</button>
    </div>
        
    </div>
</template>

<script setup> 

const props = defineProps(["numberProps"])
const emits = defineEmits(['mainusEmit', 'plusEmit'])

const plusComponent = () => {
    console.log('plusComponent');
    emits('plusEmit')

}

const mainusComponent = () => {
    console.log('mainusComponent');
    emits('mainusEmit')


}

</script> -->