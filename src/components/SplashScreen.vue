<script setup>
import { ref, onMounted } from 'vue';

const emit = defineEmits(['opened']);
const guestName = ref('guest');
const isVisible = ref(true);

onMounted(() => {
  const urlParams = new URLSearchParams(window.location.search);
  const to = urlParams.get('to');
  if (to) {
    guestName.value = to;
  }
});

const openInvitation = () => {
  isVisible.value = false;
  // allow body to scroll again if it was locked
  document.body.style.overflow = 'auto';
  emit('opened');
};

// Lock scroll while splash is active
onMounted(() => {
  document.body.style.overflow = 'hidden';
});
</script>

<template>
  <Transition name="fade">
    <div v-if="isVisible" class="splash-screen">
      <div class="splash-content">
        <div class="image-container">
          <img src="../assets/ramli.png" alt="Ramli & Nurjannah" class="splash-img" />
        </div>
        
        <div class="invitation-text">
          <p class="greeting">Hello, You're Invited</p>
          <p class="the-wedding">The Wedding Of</p>
          <h1 class="couple-names">St. Nurjannah<br/><span>&</span><br/>Ramli</h1>
          <p class="date">Senin, 15 Juni 2026</p>
          
          <div class="guest-info">
            <p class="kepada">Kepada Yth<br/>Bapak/Ibu/Saudara/i</p>
            <h2 class="guest-name">{{ guestName }}</h2>
          </div>
          
          <button @click="openInvitation" class="btn-open">
            <span class="icon">✉️</span> Buka Undangan
          </button>
        </div>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&display=swap');

.splash-screen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  /* Dark elegant red background with overlay */
  background-image: linear-gradient(rgba(25, 5, 5, 0.85), rgba(15, 5, 5, 0.95)), url('https://images.unsplash.com/photo-1507504031003-b417219a0fde?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
  background-size: cover;
  background-position: center;
  z-index: 9999;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #ffffff;
  overflow-y: auto;
  font-family: 'Playfair Display', serif;
}

.splash-content {
  text-align: center;
  padding: 2rem;
  max-width: 550px;
  width: 100%;
  animation: slideUp 1.2s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
}

.image-container {
  margin-bottom: 2rem;
  display: inline-block;
  position: relative;
}

/* Double ring elegant frame */
.image-container::before {
  content: '';
  position: absolute;
  top: -15px; left: -15px; right: -15px; bottom: -15px;
  border: 1px solid rgba(229, 57, 53, 0.3);
  border-radius: 50%;
  animation: spin 15s linear infinite;
}

.splash-img {
  width: 220px;
  height: 220px;
  object-fit: cover;
  border-radius: 50%;
  border: 3px solid #e53935; /* Red border */
  padding: 6px;
  box-shadow: 0 0 30px rgba(229, 57, 53, 0.2);
  animation: pulseRed 3s infinite ease-in-out;
  background: rgba(0,0,0,0.5);
}

.invitation-text {
  background: rgba(20, 10, 10, 0.6);
  padding: 3rem 2rem;
  border-radius: 20px;
  backdrop-filter: blur(12px);
  border: 1px solid rgba(229, 57, 53, 0.25);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
  position: relative;
}

/* Corner ornaments */
.invitation-text::before, .invitation-text::after {
  content: '✧';
  position: absolute;
  color: #ff5252;
  font-size: 1.5rem;
  opacity: 0.6;
}
.invitation-text::before { top: 15px; left: 20px; }
.invitation-text::after { bottom: 15px; right: 20px; }

.greeting {
  font-size: 1.1rem;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: #ff5252;
  margin-bottom: 1rem;
}

.the-wedding {
  font-size: 1.2rem;
  font-style: italic;
  margin-bottom: 1rem;
  color: #fbe9e7;
}

.couple-names {
  font-size: 3.2rem;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  color: #ffffff;
  text-shadow: 0 4px 10px rgba(0,0,0,0.5);
  font-weight: 600;
}

.couple-names span {
  font-size: 2rem;
  font-style: italic;
  color: #ff5252;
  font-weight: 400;
}

.date {
  font-size: 1.2rem;
  letter-spacing: 2px;
  margin-bottom: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid rgba(229, 57, 53, 0.2);
  color: #fbe9e7;
}

.guest-info {
  margin-bottom: 2.5rem;
}

.kepada {
  font-size: 0.9rem;
  letter-spacing: 1px;
  color: #ffcdd2;
  margin-bottom: 0.8rem;
  font-family: sans-serif;
  text-transform: uppercase;
}

.guest-name {
  font-size: 2rem;
  font-weight: bold;
  font-style: italic;
  color: #ff5252;
  text-transform: capitalize;
}

.btn-open {
  background: linear-gradient(135deg, #e53935 0%, #b71c1c 100%);
  color: #ffffff;
  border: 1px solid #ff8a80;
  padding: 1rem 2.5rem;
  font-size: 1.1rem;
  border-radius: 40px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 0.8rem;
  transition: all 0.4s ease;
  font-family: 'Playfair Display', serif;
  letter-spacing: 2px;
  text-transform: uppercase;
  box-shadow: 0 8px 20px rgba(229, 57, 53, 0.3);
}

.btn-open:hover {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 12px 25px rgba(229, 57, 53, 0.5);
}

.icon {
  font-size: 1.3rem;
}

/* Transitions */
.fade-leave-active {
  transition: opacity 1s ease, transform 1s ease;
}
.fade-leave-to {
  opacity: 0;
  transform: scale(1.05);
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulseRed {
  0% { box-shadow: 0 0 0 0 rgba(229, 57, 53, 0.4); }
  70% { box-shadow: 0 0 0 20px rgba(229, 57, 53, 0); }
  100% { box-shadow: 0 0 0 0 rgba(229, 57, 53, 0); }
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
</style>
