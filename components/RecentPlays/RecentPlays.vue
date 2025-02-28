<template>
    <section>
      <h3 class="text-lg font-semibold mb-4 mt-8">Ouvidas recentemente</h3>
      <div class="grid grid-cols-5 gap-4">
        <div v-for="(music, index) in musics" :key="index" class="p-4 rounded-lg">
          <img :src="music.image" class="w-full h-32 object-cover rounded-md">
          <p class="mt-2 text-sm">{{ music.name }}</p>
          <p class="text-xs text-gray-400">{{ music.artist }}</p>
        </div>
      </div>
    </section>
  </template>
  
  <script setup lang="ts">
  const musics = [
    { name: "POP!", artist: "Nayeon", image: "/nayeon.svg" },
    { name: "Bad Habit", artist: "Steve Lacy", image: "/steve.svg" },
    { name: "Gunjou", artist: "Yoasobi", image: "/gunjou.svg" },
    { name: "Flying High", artist: "JKT48", image: "/flying.svg" },
    { name: "Until I Found You", artist: "Stephen Sanchez", image: "/stephen.svg" }
  ];
  </script>
  