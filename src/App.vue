<script setup>
import { ref } from "vue";

const location = ref("Dhaka");
function getLocation(newLocation) {
  location.value = newLocation;
}
</script>

<template>
  <section class="container mx-auto flex flex-col items-center">
    <h2 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h2>
    <div class="container mx-auto flex space-x-5 justify-center m-5">
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
        @click="getLocation('Dhaka')"
      >
        Dhaka
      </button>
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
        @click="getLocation('Rajshahi')"
      >
        Rajshahi
      </button>
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
        @click="getLocation('Tangail')"
      >
        Tangail
      </button>
    </div>
    <h2 class="text-center text-2xl py-10">
      Current Location Is {{ location }}
    </h2>
  </section>
</template>

<style scoped></style>
