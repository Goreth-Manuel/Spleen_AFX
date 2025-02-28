<template>
    <div class="bg-transparent p-6 rounded-lg">
      <h2 class="text-2xl font-bold text-center">Top músicas</h2>
  
      <div class="mt-4 space-y-4">
        <div
          v-for="(music, index) in topMusics"
          :key="music.id"
          class="flex items-center justify-between bg-white/10 p-3 rounded-lg"
        >
          <div class="flex items-center space-x-4">
            <span class="text-lg font-bold">{{ String(index + 1).padStart(2, '0') }}</span>
            <img :src="music.cover" alt="Capa" class="w-12 h-12 rounded-md" />
            <div>
              <p class="font-semibold">{{ music.title }}</p>
              <p class="text-sm text-gray-300">{{ music.artist }}</p>
            </div>
          </div>
  
          <div class="flex items-center space-x-4">
            <div class="flex items-center text-gray-300">
              <HeartIcon class="w-5 h-5 mr-1" />
              <span>{{ music.likes }}</span>
            </div>
            <button class="bg-yellow-400 text-black px-3 py-1 rounded-full">
              ▶️
            </button>
          </div>
          
        </div>
       
        <div  class="relative w-full rounded-lg overflow-hidden shadow-lg">
            <img src="/premiun.svg" alt="" class="w-full object-cover">

            <h1 class="absolute text-center bottom-1 left-3 text-white text-xs px-2 py-1 rounded">Obtenha 1 mês grátis</h1>
        </div>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  import { HeartIcon } from '@heroicons/vue/24/solid';
  
  const topMusics = ref([
    { id: 1, title: 'Bad Habit', artist: 'Steve Lacy', cover: '/steve.svg', likes: 798 },
    { id: 2, title: 'Unholy', artist: 'Sam Smith', cover: '/sam.svg', likes: 429 },
    { id: 3, title: 'As It Was', artist: 'Harry Styles', cover: '/Harry.svg', likes: 826 },
    { id: 4, title: 'I Ain’t Worried', artist: 'One Republic', cover: '/one.svg', likes: 540 },
    { id: 5, title: 'Until I Found You', artist: 'Stephen Sanchez', cover: '/stephen.svg', likes: 196 },
  ]);
  </script>
  
  <style scoped>
  </style>
  