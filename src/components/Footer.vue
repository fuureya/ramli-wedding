<script setup>
</script>

<template>
  <footer class="footer">
    <div class="footer-content">
      <h2 class="footer-logo" style="color: white;">St. Nurjannah <br> & <br> Ramli</h2>
      
      <nav class="footer-nav">
        <a href="#story">Our Story</a>
        <a href="#celebration">The Celebration</a>
        <a href="#gift">Wedding Gift</a>
      </nav>
      
      <p class="footer-credit" style="color: white; opacity: 1;">
        Designed with <b><a href="https://medium.com/@fuureya">fuureya</a></b> <br>
        &copy; 2026 St. Nurjannah & Ramli. All rights reserved.
      </p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: var(--color-primary);
  color: var(--color-white);
  padding: 60px 20px 40px;
  text-align: center;
}

.footer-content {
  max-width: 800px;
  margin: 0 auto;
}

.footer-logo {
  font-size: 2.5rem;
  margin-bottom: 30px;
  font-style: italic;
}

.footer-nav {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-bottom: 40px;
}

.footer-nav a {
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 1px;
  opacity: 0.8;
}

.footer-nav a:hover {
  opacity: 1;
  color: var(--color-gold);
}

.footer-credit {
  font-size: 0.8rem;
  line-height: 1.8;
  border-top: 1px solid rgba(255,255,255,0.1);
  padding-top: 20px;
}
</style>
