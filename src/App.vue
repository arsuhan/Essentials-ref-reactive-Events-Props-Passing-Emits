<script setup>
import { RouterView } from "vue-router";
// import Component1 from "./components/Component1.vue";
// import Component2 from "./components/Component2.vue";
import { ref, reactive } from "vue";
import Handlr1 from "./views/handlr1.vue";
import Handlr2 from "./views/Handlr2.vue";
// import { stat } from "node:fs/promises";

// start views

const number = ref(0);

const state = reactive({
    formValue : ""
})

const clear = () => {
    state.formValue = ""
}

const plus = () => {
  number.value = number.value + 1
}

const mainus = () => {
  if (number.value > 0) {    
    number.value = number.value - 1
  }
}


</script>

<template>
  <div class="bg-sky-700 p-4 text-3xl">
    <h1>Gloval component</h1>
    <input
      type="text"
      placeholder="anithing text"
      class="p-2 text-white bg-cyan-200 border mt-4"
      v-model="state.formValue"
    />
    <div class="flex justify-center">
      <button
        type="text"
        placeholder="anyhting text"
        class="border bg-amber-300 rounded-3xl p-2 mx-3"
        @click="plus"
      >
        +
      </button>
      <p class="p-2 bg-amber-950 text-white">{{ number }}</p>
      <button
        type="text"
        placeholder="anyhting text"
        class="border bg-amber-500 rounded-3xl p-2 mx-3"
        @click="mainus"
      >
        -
      </button>
    </div>
  </div>

  <div class="flex justify-between">
    <Handlr1 :props-number="number" @plusEmit="plus" @mainusEmit="mainus" />
    <Handlr2 :inputProps="state.formValue" @clear-emit="clear" />
  </div>

</template>

<style scoped></style>
