<script setup>
import { ref, watch } from 'vue';
import musicFile from '../assets/lagu.mp3';

const props = defineProps({
  shouldPlay: {
    type: Boolean,
    default: false
  }
});

const isPlaying = ref(false);
const audioRef = ref(null);

watch(() => props.shouldPlay, (newVal) => {
  if (newVal) {
    playAudio();
  }
});

const playAudio = () => {
  if (audioRef.value) {
    audioRef.value.play().then(() => {
      isPlaying.value = true;
    }).catch((err) => {
      console.error("Autoplay prevented:", err);
    });
  }
};

const togglePlay = () => {
  if (audioRef.value) {
    if (isPlaying.value) {
      audioRef.value.pause();
      isPlaying.value = false;
    } else {
      audioRef.value.play();
      isPlaying.value = true;
    }
  }
};
</script>

<template>
  <div class="music-player" @click="togglePlay" :class="{ 'playing': isPlaying }">
    <div class="disc">
      <div class="disc-center"></div>
    </div>
    <div class="music-icon">
      <span v-if="isPlaying">⏸</span>
      <span v-else>▶</span>
    </div>
    <audio ref="audioRef" :src="musicFile" loop preload="auto"></audio>
  </div>
</template>

<style scoped>
.music-player {
  position: fixed;
  bottom: 30px;
  right: 30px;
  width: 50px;
  height: 50px;
  background: var(--color-primary, #e53935);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  z-index: 9900;
  box-shadow: 0 4px 15px rgba(229, 57, 53, 0.4);
  transition: transform 0.3s ease, background 0.3s ease;
}

.music-player:hover {
  transform: scale(1.1);
}

.disc {
  position: absolute;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: 2px dashed rgba(255, 255, 255, 0.5);
  animation: spin 4s linear infinite;
  animation-play-state: paused;
}

.music-player.playing .disc {
  animation-play-state: running;
}

.disc-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 10px;
  height: 10px;
  background: white;
  border-radius: 50%;
}

.music-icon {
  position: relative;
  z-index: 2;
  color: white;
  font-size: 14px;
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@media (max-width: 768px) {
  .music-player {
    bottom: 20px;
    right: 20px;
    width: 45px;
    height: 45px;
  }
}
</style>
