<script setup>
const bgOrange = "bg-orange-400";
const bgIndogo = "bg-indigo-400";
const bgGreen = "bg-green-400";
const textRed = "color:red;";
const textWhite = "color:white;";

const color = {
  backgroundColor: "green",
  border: "1px solid orange",
};

const weekday = false;

const colors = {
  bgcolor: "bg-teal-100",
  bordercolor: "border-teal-500",
  textcolor: "text-teal-900",
};

const messageType = "success";

if (messageType == "error") {
  colors.bgcolor = "bg-red-200";
  colors.bordercolor = "bg-red-200";
  colors.textcolor = "bg-red-200";
}
if (messageType == "warning") {
  colors.bgcolor = "bg-orange-200";
  colors.bordercolor = "bg-orange-200";
  colors.textcolor = "bg-orange-200";
}
</script>

<template>
  <section class="container mx-auto">
    <h1 class="text-center text-3xl py-12">Class & Style Binding</h1>
    <section class="flex space-x-10">
      <div class="w-1/3 h-16" :class="bgOrange"></div>
      <div class="w-1/3 h-16" :class="bgIndogo"></div>
      <div class="w-1/3 h-16" :class="bgGreen"></div>
    </section>
    <section class="mt-10">
      <div
        class="h-16 flex items-center justify-center"
        :class="[
          weekday == true ? 'bg-red-600' : 'bg-green-600',
          weekday == true ? 'text-2xl' : 'text-4xl',
        ]"
        :style="textWhite"
      >
        It's a weekday!
      </div>
    </section>
    <section class="mt-10">
      <div
        class="border-t-4 rounded-b px-4 py-4 shadow-md"
        :class="[colors.bgcolor, colors.bordercolor, colors.textcolor]"
      >
        <P class="font-bold">The form contains two input fields:</P>
        <P class="text-sm">This version adds</P>
      </div>
    </section>
    <section class="mt-10">
      <div class="h-16 flex items-center justify-center" :style="color"></div>
    </section>
  </section>
</template>

<style scoped></style>
