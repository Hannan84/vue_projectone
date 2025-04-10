<script setup>
import { ref, onMounted, nextTick } from "vue";

// carousel
const items = ref([
  "https://plus.unsplash.com/premium_photo-1669315453542-68167fe4a83b?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  "https://plus.unsplash.com/premium_photo-1668017178993-4c8fc9f59872?q=80&w=1471&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  "https://plus.unsplash.com/premium_photo-1661836692294-755ebc98f9bc?q=80&w=1283&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  "https://plus.unsplash.com/premium_photo-1675448891102-6b8c6faffc3c?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  "https://plus.unsplash.com/premium_photo-1700169409644-b908a5ba3547?q=80&w=1478&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
]);

let carousel = null;

const newItem = ref(
  "https://images.unsplash.com/photo-1742222168686-55ec5ffd3c81?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
);

function addNewItem() {
  items.value.push(newItem.value);
  carousel.destroy();
  nextTick(function () {
    carousel = new Flickity("#carousel", {});
  });
}

onMounted(() => {
  carousel = new Flickity("#carousel", {});
});

// pie chart

const newChart = ref(16);

let chart = null;

const dataset = [100, 100, 100];

const data = {
  labels: ["Red", "Blue", "Yellow"],
  datasets: [
    {
      label: "My Dataset",
      data: dataset,
      backgroundColor: [
        "rgb(255, 99, 132)",
        "rgb(54, 162, 235)",
        "rgb(255, 205, 86)",
        "rgb(43, 105, 86)",
        "rgb(21, 21, 186)",
        "rgb(55, 155, 75)",
      ],
      hoverOffset: 4,
    },
  ],
};

const config = {
  type: "pie",
  data: data,
};

onMounted(() => {
  const ctx = document.getElementById("myChart");
  chart = new Chart(ctx, config);
});

function updateChart() {
  dataset.push(newChart.value);
  chart.data.datasets[0].data = dataset;
  chart.update();
}

// location information
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
    <p class="text-center text-xl py-10" v-show="location == 'Dhaka'">
      Dhaka is the capital and largest city of Bangladesh, known for its rich
      history, vibrant culture, and rapid urban development. It is one of the
      most densely populated cities in the world, serving as the country's
      political, economic, and cultural hub.
    </p>
    <p class="text-center text-xl py-10" v-show="location == 'Rajshahi'">
      Rajshahi is a major city in northwestern Bangladesh, known for its silk
      industry, mangoes, and educational institutions. It is one of the most
      historically and culturally rich cities in the country and serves as the
      administrative center of Rajshahi Division.
    </p>
    <p class="text-center text-xl py-10" v-show="location == 'Tangail'">
      Tangail is a district in central Bangladesh, located in the Dhaka
      Division. It is known for its handloom industry, rich history, and
      cultural heritage. The district plays a significant role in Bangladesh’s
      agriculture, textiles, and trade.
    </p>
  </section>

  <div class="my-10">
    <h2 class="text-center text-2xl py-10">Flickity Carousel</h2>
    <input class="py-2 px-4 border" type="text" v-model="newItem" />
    <button
      @click="addNewItem()"
      class="ml-2 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4"
    >
      Button
    </button>
  </div>
  <div class="mx-auto items" id="carousel">
    <div
      :style="`background-image:url(${item})`"
      class="item"
      v-for="(item, index) in items"
      :key="item"
    ></div>
  </div>
  <h2 class="text-center text-2xl py-10">Pie Chart using chart.js</h2>
  <div class="mx-auto w-[400px] h-[400px] bg-gray-400">
    <canvas id="myChart"></canvas>
  </div>
  <div class="my-10">
    <input class="py-2 px-4 border" type="text" v-model="newChart" />
    <button
      @click="updateChart()"
      class="ml-2 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4"
    >
      Button
    </button>
  </div>
</template>

<style scoped>
.items {
  width: 600px;
  height: 400px;
}

.item {
  width: 600px;
  height: 400px;
  background-color: #ccc;
  background-size: cover;
}
</style>
