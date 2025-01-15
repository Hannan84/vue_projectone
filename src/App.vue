<script setup>
const items = [1, 2, 3, 4, 5];
</script>

<template>
  <section class="container mx-auto flex flex-col items-center space-y-2">
    <!-- <div class="p-5 border border-gray-600 w-40" v-for="item in items">
      {{ item }}
    </div> -->
    <div class="p-5 border border-gray-600 w-40" v-for="n in 5">
      {{ n }}
    </div>
  </section>
</template>

<style scoped></style>
