<script setup>
</script>

<template>
  <section class="section-container" id="story">
    <div class="story-icon mb-4">
      <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="var(--color-gold)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
        <path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path>
      </svg>
    </div>
    <h2 class="section-title">Our Story</h2>
    
    <div class="story-content mt-4">
      <p class="quote mb-4">
        "Cinta sejati bukan tentang menemukan seseorang yang sempurna, melainkan tentang melihat kesempurnaan dalam ketidaksempurnaan bersama."
      </p>
      
      <p class="story-text">
        Berawal dari sebuah pertemuan yang sederhana, kami tidak pernah menyangka bahwa langkah kecil tersebut akan membawa kami pada perjalanan yang begitu indah. Seiring waktu, kami saling mengenal, berbagi cerita, tawa, dan mimpi. Bersama, kami belajar untuk tumbuh, menghadapi berbagai tantangan, dan saling menguatkan dalam setiap keadaan.
        <br><br>
        Kini, dengan penuh rasa syukur dan kebahagiaan, kami siap melangkah ke babak baru kehidupan sebagai pasangan suami istri. Kami merasa terhormat dapat berbagi momen istimewa ini bersama keluarga dan sahabat tercinta.
      </p>
    </div>

    <div class="story-image-container mt-4">
      <img src="https://images.unsplash.com/photo-1522673607200-164d1b6ce486?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Holding Hands" class="story-image" />
    </div>
  </section>
</template>

<style scoped>
.story-icon {
  display: flex;
  justify-content: center;
}

.quote {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.4rem;
  color: var(--color-primary);
  margin: 30px 0;
}

.story-text {
  font-size: 1rem;
  color: #555;
  max-width: 600px;
  margin: 0 auto 40px auto;
  line-height: 1.8;
}

.story-image-container {
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
  overflow: hidden;
  border-radius: var(--border-radius);
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

.story-image {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.5s ease;
}

.story-image-container:hover .story-image {
  transform: scale(1.05);
}
</style>
