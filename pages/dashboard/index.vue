<template>
    <div class=" flex min-h-screen text-white"
    :style="{
      background: 'linear-gradient(235.64deg, #4831A2 -1.78%, rgba(13, 7, 39, 0.9) 52.42%, #1F1153 134.35%)',
    }">

        <Sidebar />
       
        <div class="w-full">
            <Header />
            <div class="w-full pl-6">
                <div class="flex justify-between">
                    <div class="w-full pt-10">

                        <HeroSection />
                        <RecentPlays />
                        <MusicReleases />
        
                        <MoodSection />
                    </div>

                    <div class="w-7xl pl-6">
                        <TopMusics />
                    </div>
                </div>

            </div>

         
        </div>
    </div>
  <footer>
    <MusicPlayer />
  </footer>
  </template>

<script setup lang="ts">
import Header from "../../components/Header/Header.vue";
</script>
  
