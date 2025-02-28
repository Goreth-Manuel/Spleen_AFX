<script setup lang="ts">
import { ref } from "vue";

interface Music {
  title: string;
  artist: string;
  releaseDate: string;
  cover: string;
}

const musics = ref<Music[]>([
  {
    title: "DICE",
    artist: "Nmixx",
    releaseDate: "10-20-2022",
    cover: "/dice.svg",
  },
  {
    title: "28 Reasons",
    artist: "Seulgi",
    releaseDate: "TBA",
    cover: "/reasons.svg",
  },
]);
</script>

<template>
  <div>
    <div class="flex justify-between items-center mb-4">
      <h2 class="text-2xl font-semibold mt-8">Novas músicas por lançar</h2>
      <div class="space-x-2">
        <button class="p-2 bg-gray-700 rounded-full hover:bg-gray-600">⬅️</button>
        <button class="p-2 bg-gray-700 rounded-full hover:bg-gray-600">➡️</button>
      </div>
    </div>

    <div class="flex gap-4 overflow-x-auto scrollbar-hide">
      <div
        v-for="(music, index) in musics"
        :key="index"
        class="relative w-full bg-gray-800 rounded-lg overflow-hidden shadow-lg"
      >
        <img :src="music.cover" alt="Cover" class="w-full h-90 object-cover" />
        <div class="absolute top-2 left-2 bg-yellow-500 text-black text-xs px-2 py-1 rounded">
          Sneak Peak
        </div>
        <div class="w-full absolute bottom-2 left-2 p-6">
          <h3 class="text-lg font-semibold">{{ music.title }}</h3>
          <p class="text-gray-400">{{ music.artist }}</p>
          <p class="text-sm">{{ music.releaseDate }}</p>
          <button class="absolute bottom-2 right-8 bg-yellow-500 p-2 rounded-full">
            ▶️
          </button>
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
