<script setup lang="ts">
// import SidebarItem from "./SidebarItem.vue";
import { LayoutDashboard, Album, Mic, Music, Heart, Settings, Users, HelpCircle } from "lucide-vue-next";

const menuItems = [
  { title: "Dashboard", icon: LayoutDashboard, active: true },
  { title: "Álbum", icon: Album },
  { title: "Artista", icon: Mic },
  { title: "Músicas", icon: Music },
  { title: "Favoritos", icon: Heart },
];

const supportItems = [
  { title: "Configurações", icon: Settings },
  { title: "Comunidade", icon: Users },
  { title: "Ajuda e Suporte", icon: HelpCircle },
];
</script>

<template>
  <aside class="w-64 h-screen bg-[#0C0C1D] text-white flex flex-col p-4">
    <!-- Logo -->
    <div class="flex items-center gap-2 mb-6">
      <span class="text-yellow-400 text-2xl font-bold">S</span>
      <span class="text-lg font-semibold">Spleen AFX</span>
    </div>

    <!-- Menu Principal -->
    <span class="text-gray-400 text-xs mb-2">Menu Principal</span>
    <div class="space-y-2">
      <SidebarItem v-for="item in menuItems" :key="item.title" v-bind="item" />
    </div>

    <!-- Suporte -->
    <span class="text-gray-400 text-xs mt-6 mb-2">Suporte</span>
    <div class="space-y-2">
      <SidebarItem v-for="item in supportItems" :key="item.title" v-bind="item" />
    </div>
  </aside>
</template>
