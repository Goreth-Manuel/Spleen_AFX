<script setup lang="ts">
import { ref } from "vue";

interface Mood {
  title: string;
  description: string;
  image: string;
}

const moods = ref<Mood[]>([
  {
    title: "Semangat Pagi",
    description: "Menemani sarapan dengan lagu hits",
    image: "/panquecas.svg",
  },
  {
    title: "Sad Banget",
    description: "Jangan ditahan nangis aja",
    image: "/uva.svg",
  },
  {
    title: "Mager Banget",
    description: "Asik-in aja magernya dengan musik hits",
    image: "/gato.svg",
  },
  {
    title: "I Love You",
    description: "I love you so much, hope you’ll know it",
    image: "/maos.svg",
  },
  {
    title: "Nugas Nih",
    description: "Nugas sambil ditemenin lagu memang asik",
    image: "/nugas.svg",
  },
]);
</script>

<template>
  <div>
    <div class="flex justify-between items-center mb-8">
      <h2 class="text-2xl font-semibold mt-8">Mood</h2>
      <div class="space-x-2">
        <button class="p-2 rounded-full hover:bg-gray-600">⬅️</button>
        <button class="p-2  rounded-full hover:bg-gray-600">➡️</button>
      </div>
    </div>

    <div class=" flex gap-4 overflow-x-auto scrollbar-hide pb-30">
      <div
        v-for="(mood, index) in moods"
        :key="index"
        class="relative w-full rounded-lg overflow-hidden shadow-lg"
      >
        <img :src="mood.image" alt="Mood" class="w-full h-40 object-cover" />
        <div class="absolute top-2 left-2 bg-opacity-75 text-white text-xs px-2 py-1 rounded">
          {{ mood.title }}
        </div>
        <div class="p-3">
          <h3 class="text-lg font-semibold">{{ mood.title }}</h3>
          <p class="text-sm text-gray-400">{{ mood.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
</style>
