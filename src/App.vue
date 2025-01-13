<script setup>
import { ref } from "vue";
const location = "Dhaka";
const weather = ref("s");
</script>

<template>
  <section class="container mx-auto flex flex-col items-center">
    <h1 class="text-4xl mb-10">Data Project</h1>
    <div class="w-1/3 bg-gray-200 flex space-y-10 p-10 flex-col items-center">
      <h1 class="text-3xl">{{ location }}</h1>
      <template v-if="weather == 's'">
        <h2 class="text-2xl">Weather: Sunny</h2>
        <img id="sunny" src="./data/icon/weather-sunny-icon.png" alt="" />
      </template>
      <template v-if="weather == 'pc'">
        <h2 class="text-2xl">Weather: Partly Cloudy</h2>
        <img src="./data/icon/weather-cloud-icon.png" alt="" />
      </template>
      <template v-if="weather == 'r'">
        <h2 class="text-2xl">Weather: Rainy</h2>
        <img src="./data/icon/weather-rain-icon.png" alt="" />
      </template>
      <template v-if="weather == 't'">
        <h2 class="text-2xl">Weather: Thunderstorm</h2>
        <img src="./data/icon/weather-storm-icon.png" alt="" />
      </template>
      <template v-if="weather == 'c'">
        <h2 class="text-2xl">Weather: Cyclone</h2>
        <img src="./data/icon/weather-cyclone-icon.png" alt="" />
      </template>
      <input type="text" name="" id="" class="text-center" v-model="weather" />
    </div>
  </section>
</template>

<style scoped></style>
