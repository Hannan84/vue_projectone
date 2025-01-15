<script setup>
const tasks = [
  "Project Planning and Strategy",
  "Team Collaboration and Coordination",
  "Market Research and Analysis",
  "Customer Feedback and Improvement",
  "Data Collection and Reporting",
];
</script>

<template>
  <section class="container mx-auto flex flex-col items-center space-y-2">
    <div class="p-5 border border-gray-600 w-50" v-for="(task, index) in tasks">
      {{ index + 1 }}. {{ task }}
    </div>
  </section>
</template>

<style scoped></style>
