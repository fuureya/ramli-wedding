<script setup>
</script>

<template>
  <section class="hero">
    <div class="hero-overlay"></div>
    <div class="hero-content fade-in-up">
      <h1 class="couple-name">St. Nurjanah & Ramli</h1>
      <p class="subtitle">ARE GETTING MARRIED | 15 Juni 2026</p>
      <a href="https://www.google.com/calendar/render?action=TEMPLATE&text=St.+Nurjannah+%26+Ramli+Wedding&location=https%3A%2F%2Fwww.google.com%2Fmaps%2Fplace%2FJl.%2BCendana%2B2%2C%2BSulawesi%2BSelatan%2B90562%2F%40-5.1380349%2C119.5233545%2C17z%2Fdata%3D%213m1%214b1%214m6%213m5%211s0x2dbee4b2c5301277%3A0xbe3e5ccbfca13e41%218m2%213d-5.1380402%214d119.5259294%2116s%252Fg%252F11f647tzmk%3Fentry%3Dttu%26g_ep%3DEgoyMDI2MDYwMy4xIKXMDSoASAFQAw%253D%253D&dates=20260615T010000Z%2F20260615T150000Z" class="btn-primary mt-4" target="_blank">Add to Calendar</a>
    </div>
  </section>
</template>

<style scoped>
.hero {
  height: 100vh;
  width: 100%;
  position: relative;
  background-image: url('../assets/ramli.png'); /* Beautiful wedding placeholder */
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(0,0,0,0.3) 0%, rgba(0,0,0,0.6) 100%);
}

.hero-content {
  position: relative;
  z-index: 10;
  color: var(--color-white);
  padding: 0 20px;
}

.couple-name {
  font-size: 5rem;
  margin-bottom: 10px;
  color: var(--color-white);
  text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  line-height: 1.1;
}

.subtitle {
  font-family: var(--font-sans);
  font-size: 1rem;
  letter-spacing: 3px;
  margin-bottom: 30px;
  text-transform: uppercase;
}

@media (max-width: 768px) {
  .couple-name {
    font-size: 3.5rem;
  }
  .subtitle {
    font-size: 0.8rem;
    letter-spacing: 2px;
  }
}
</style>
