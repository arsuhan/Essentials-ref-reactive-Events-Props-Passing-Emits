<script setup>
import { RouterView } from "vue-router";
import Component1 from "./components/Component1.vue";
import Component2 from "./components/Component2.vue";
import { ref, reactive } from "vue";

const number = ref(0)

const state = reactive ({
    formValue : ""
})

const plus = () => {
  number.value = number.value + 1
}

const mainus = () => {
  if(number.value > 0){

    number.value = number.value - 1
  }
}

const clear = () => {

  state.formValue = ""
}

</script>

<template>
  <div class="bg-cyan-400 p-6 text-4xl">
    <h1 class="text-3xl p-4">Gloval Component</h1>
    <input
      type="text"
      placeholder="tuor text"
      class="p-2 text-white bg-amber-400 mt-4" v-model="state.formValue"
    />
    <div class="flex p-4 justify-center">
      <button @click="plus" class="bg-green-500 p-2 text-3xl rounded-full mx-2">+</button>
      <p class="p-2 bg-amber-300 text-black">{{ number }}</p>
      <button @click="mainus" class="bg-green-500 p-2 text-3xl rounded-full mx-2">-</button>
    </div>
  </div>

  <!-- <RouterView /> -->
  <div class="flex justify-between">
    <Component1 :numberProps="number" @plusEmit="plus" @mainusEmit="mainus" />
    <Component2 :input-props="state.formValue" @clearEmit="clear" />
  </div>
</template>

<style scoped></style>
