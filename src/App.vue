<script setup>
const location = "Dhaka";
const weather = "t";
</script>

<template>
  <section class="container mx-auto flex flex-col p-10 items-center">
    <h1 class="text-4xl mb-10">Data Project</h1>
    <div class="flex space-y-4 p-10 bg-gray-200 flex-col w-1/3 items-center">
      <h1 class="text-3xl">{{ location }}</h1>
      <h2 class="text-2xl" v-show="weather == 's'">Weather: Sunny</h2>
      <h2 class="text-2xl" v-show="weather == 'pc'">Weather: Partly Cloudy</h2>
      <h2 class="text-2xl" v-show="weather == 'r'">Weather: Rainy</h2>
      <h2 class="text-2xl" v-show="weather == 't'">Weather: Thunderstorm</h2>
      <h2 class="text-2xl" v-show="weather == 'c'">Weather: Cyclone</h2>
      <img
        v-show="weather == 's'"
        src="./data/icon/weather-sunny-icon.png"
        alt=""
      />
      <img
        v-show="weather == 'pc'"
        src="./data/icon/weather-cloud-icon.png"
        alt=""
      />
      <img
        v-show="weather == 'r'"
        src="./data/icon/weather-rain-icon.png"
        alt=""
      />
      <img
        v-show="weather == 't'"
        src="./data/icon/weather-storm-icon.png"
        alt=""
      />
      <img
        v-show="weather == 'c'"
        src="./data/icon/weather-cyclone-icon.png"
        alt=""
      />
    </div>
  </section>
</template>

<style scoped></style>
