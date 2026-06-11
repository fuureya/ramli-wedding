<script setup>
</script>

<template>
  <section class="celebration-section bg-light" id="celebration">
    <div class="section-container">
      <h2 class="section-title">The Celebration</h2>
      
      <div class="cards-container mt-4">
        <!-- Ceremony Card -->
        <div class="event-card">
          <div class="event-icon">💍</div>
          <h3 class="event-title">Akad Nikah</h3>
          <p class="event-time">09:00 WITA</p>
          <div class="event-divider"></div>
          <p class="event-location">BTP Blok AF</p>
          <p class="event-address">Jl. Cendana 2 Samping Pasar Sentral BTP</p>
          <a href="https://maps.app.goo.gl/cAF8sbstyFxLFqbL9" class="btn-outline mt-4">See On Map</a>
        </div>

        <!-- Reception Card -->
        <div class="event-card">
          <div class="event-icon">🥂</div>
          <h3 class="event-title">Resepsi</h3>
          <p class="event-time">09:00 WITA</p>
          <div class="event-divider"></div>
          <p class="event-location">BTP Blok AF</p>
          <p class="event-address">Jl. Cendana 2 Samping Pasar Sentral BTP</p>
          <a href="https://maps.app.goo.gl/cAF8sbstyFxLFqbL9" class="btn-outline mt-4">See On Map</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.celebration-section {
  background-color: #f1ebe5; /* Slightly darker cream for contrast */
  padding: 40px 0;
}

.cards-container {
  display: flex;
  gap: 30px;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 50px;
}

.event-card {
  background: var(--color-white);
  padding: 50px 30px;
  border-radius: var(--border-radius);
  box-shadow: 0 10px 25px rgba(0,0,0,0.05);
  flex: 1;
  min-width: 300px;
  max-width: 350px;
  text-align: center;
  transition: transform var(--transition-speed), box-shadow var(--transition-speed);
}

.event-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.1);
}

.event-icon {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.event-title {
  font-size: 1.8rem;
  margin-bottom: 10px;
}

.event-time {
  font-family: var(--font-sans);
  color: var(--color-primary);
  font-weight: 500;
  letter-spacing: 1px;
}

.event-divider {
  width: 40px;
  height: 1px;
  background-color: #ddd;
  margin: 20px auto;
}

.event-location {
  font-weight: 600;
  font-size: 1.1rem;
  margin-bottom: 5px;
}

.event-address {
  color: #777;
  font-size: 0.9rem;
}

.btn-outline {
  display: inline-block;
  padding: 10px 20px;
  border: 1px solid var(--color-primary);
  color: var(--color-primary);
  border-radius: 4px;
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 1px;
  transition: all 0.3s;
}

.btn-outline:hover {
  background-color: var(--color-primary);
  color: var(--color-white);
}

@media (max-width: 768px) {
  .cards-container {
    flex-direction: column;
    align-items: center;
  }
}
</style>
