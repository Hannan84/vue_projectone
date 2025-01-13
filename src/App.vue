<script setup>
const number = 16;
const animal = "Tiger";
const searchUrl = "https://www.pexels.com/search/";
</script>

<template>
  <section class="container mx-auto p-10">
    <h1 class="text-4xl mb-10">Data Project</h1>
    <h2 class="text-2xl mb-10">{{ number }} / 4 = {{ number / 4 }}</h2>
    <h2 class="text-2xl mb-10">
      {{ number }} is {{ number % 2 == 0 ? "even" : "odd" }}
    </h2>
    <h2 class="text-2xl mb-10">
      <a :href="searchUrl + animal.toLowerCase()" target="_blank"
        >Search for {{ animal }}</a
      >
    </h2>
  </section>
</template>

<style scoped></style>
