<script setup>
import { ref } from "vue";
import JSConfetti from "js-confetti";

const name = "hola";
const variable = "Pa´ Pa´ namericano";
let counter = ref(0);

let characters = ref([]);

function add() {
  counter.value++;
  characters.value.push(counter.value);
}
function remove() {
  counter.value--;
  characters.value.pop();
  if (counter.value < 0) {
    counter.value = 0;

    window.alert("Ya no tengo nada :(");
  }
}
</script>

<template>
  <div
    class="bg-purple-600 font-semibold font-serif rounded mx-auto max-w-96 py-4 px-6"
  >
    Hola...... {{ variable }}

    <div
      v-if="counter > 0"
      class="bg-green-500 rounded-full size-11 shadow-black shadow-xl flex justify-center items-center"
    >
      <var>{{ counter }}</var>
    </div>
    <div v-else="(counter = 0)">hola</div>
    <div class="flex gap-4">
      <button
        @click="remove"
        class="bg-blue-500 rounded-full size-4 shadow-black shadow-xl flex justify-center items-center"
      >
        -
      </button>

      <button
        @click="add"
        class="bg-blue-500 rounded-full size-4 shadow-black shadow-xl flex justify-center items-center"
      >
        +
      </button>
    </div>
  </div>


  <div v-for="(name,index) in characters"
  :key="index"

   class="bg-orange-400 mt-1 text-center">
   {{ name }}
   </div>
</template>
