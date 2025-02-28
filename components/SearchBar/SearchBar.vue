<script setup lang="ts">
import { ref } from "vue";
import { Search } from "lucide-vue-next";

const searchQuery = ref("");
</script>

<template>
  <div class="relative w-full max-w-7xl">
    <input
      v-model="searchQuery"
      type="text"
      placeholder="Pesquisar álbum, música ou artista"
      class="w-7xl py-2 pl-4 pr-10 rounded-lg border-none focus:ring-2 focus:ring-blue-400 bg-white text-gray-900 shadow-md"
    />
    <Search class="absolute ml-8 right-3 top-1/2 transform -translate-y-1/2 text-gray-500" />
  </div>
</template>
