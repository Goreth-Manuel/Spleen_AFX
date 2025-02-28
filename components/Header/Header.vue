<script setup lang="ts">
import SearchBar from "../SearchBar/SearchBar.vue";
import UserProfile from "../UserProfile/UserProfile.vue";

const user = {
  name: "Jerome Bell",
  email: "jeromebell@gmail.com",
  avatar: "https://i.pravatar.cc/150?img=5",
};
</script>

<template>
  <header class="flex justify-between items-center px-6 py-3 bg-gradient-to-r from-[#0C0C1D] to-[#211A50] shadow-lg">
    <SearchBar />
    <UserProfile :user="user" />
  </header>
</template>
