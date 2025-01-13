<script setup>
const images = [
  {
    image:
      "//images.unsplash.com/photo-1506744038136-46273834b3fb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
    title: "Surrounded by trees and mountains",
    link: "https://unsplash.com/photos/NRQV-hBF10M",
  },
  {
    image:
      "//images.unsplash.com/photo-1506744038136-46273834b3fb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
    title: "Water by mountains",
    link: "https://unsplash.com/photos/NRQV-hBF10M",
  },
  {
    image:
      "//images.unsplash.com/photo-1506744038136-46273834b3fb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
    title: "Trees and mountains",
    link: "https://unsplash.com/photos/NRQV-hBF10M",
  },
];
</script>

<template>
  <section class="container mx-auto p-10">
    <h1 class="text-4xl mb-10">Data Project</h1>
    <section class="main flex space-x-4">
      <div class="flex space-y-4 flex-col w-1/2">
        <img v-bind:title="images[0].title" :src="images[0].image" alt="" />
        <h2 class="text-xl text-left">{{ images[0].title }}</h2>
        <a
          target="_blank"
          v-bind:href="images[0].link"
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded w-40 text-center"
        >
          Image Source
        </a>
      </div>
      <div class="flex space-y-4 flex-col w-1/2">
        <img v-bind:title="images[1].title" :src="images[1].image" alt="" />
        <h2 class="text-xl text-left">{{ images[1].title }}</h2>
        <a
          target="_blank"
          v-bind:href="images[1].link"
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded w-40 text-center"
        >
          Image Source
        </a>
      </div>
      <div class="flex space-y-4 flex-col w-1/2">
        <img v-bind:title="images[2].title" :src="images[2].image" alt="" />
        <h2 class="text-xl text-left">{{ images[2].title }}</h2>
        <a
          target="_blank"
          v-bind:href="images[2].link"
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded w-40 text-center"
        >
          Image Source
        </a>
      </div>
    </section>
  </section>
</template>

<style scoped></style>
