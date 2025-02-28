<script setup lang="ts">
import { defineProps } from "vue";

defineProps<{
  icon: any; // Componente do ícone
  title: string;
  active?: boolean;
}>();
</script>

<template>
  <div
    class="flex items-center gap-3 px-4 py-2 rounded-md cursor-pointer transition-colors"
    :class="active ? 'bg-yellow-400 text-black font-semibold' : 'text-gray-300 hover:text-white hover:bg-gray-800'"
  >
    <component :is="icon" class="w-5 h-5" />
    <span class="text-sm">{{ title }}</span>
  </div>
</template>
