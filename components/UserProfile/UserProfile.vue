<script setup lang="ts">
import { ChevronDown } from "lucide-vue-next";

defineProps<{
  user: {
    name: string;
    email: string;
    avatar: string;
  };
}>();
</script>

<template>
  <div class="flex items-center space-x-3">
    <img :src="user.avatar" alt="Avatar" class="w-10 h-10 rounded-full" />
    <div class="text-white text-sm">
      <p class="font-semibold">{{ user.name }}</p>
      <p class="text-gray-300 text-xs">{{ user.email }}</p>
    </div>
    <ChevronDown class="text-white w-5 h-5" />
  </div>
</template>
