<script setup>
import { ref } from 'vue'
import SplashScreen from './components/SplashScreen.vue'
import HeroSection from './components/HeroSection.vue'
import OurStory from './components/OurStory.vue'
import Celebration from './components/Celebration.vue'
import WeddingGift from './components/WeddingGift.vue'
import Footer from './components/Footer.vue'
import MusicPlayer from './components/MusicPlayer.vue'

const isMusicPlaying = ref(false)

const startMusic = () => {
  isMusicPlaying.value = true
}
</script>

<template>
  <SplashScreen @opened="startMusic" />
  <MusicPlayer :shouldPlay="isMusicPlaying" />
  <main class="app-container">
    <HeroSection />
    <OurStory />
    <Celebration />
    <WeddingGift />
    <Footer />
  </main>
</template>

<style scoped>
.app-container {
  width: 100%;
  max-width: 100vw;
  overflow-x: hidden;
}
</style>
