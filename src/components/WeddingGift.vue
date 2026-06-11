<script setup>
const copyToClipboard = (text) => {
  navigator.clipboard.writeText(text).then(() => {
    alert('Account number copied to clipboard!')
  })
}
</script>

<template>
  <section class="section-container" id="gift">
    <h2 class="section-title">Wedding Gift</h2>
    <p class="gift-text mt-4">
      Kehadiran dan doa restu Bapak/Ibu/Saudara/i merupakan hadiah terindah bagi kami. Namun, apabila berkenan memberikan tanda kasih, kami telah menyediakan informasi rekening di bawah ini. Atas segala perhatian, doa, dan kebaikan hati Anda, kami mengucapkan terima kasih yang sebesar-besarnya.
    </p>

    <div class="gift-cards mt-8">
    
      <!-- Mandiri Card -->
      <div class="bank-card">
        <div class="bank-logo mandiri">Mandiri</div>
        <p class="account-name">Ramli</p>
        <p class="account-number">1740 0120 45431</p>
        <button class="btn-copy" @click="copyToClipboard('1740012045431')">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="9" y="9" width="13" height="13" rx="2" ry="2"></rect>
            <path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"></path>
          </svg>
          COPY
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.gift-text {
  max-width: 650px;
  margin: 0 auto;
  color: #555;
}

.gift-cards {
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
}

.bank-card {
  background: var(--color-white);
  border: 1px solid #eee;
  padding: 40px;
  border-radius: 12px;
  text-align: center;
  min-width: 280px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.03);
  transition: transform 0.3s, box-shadow 0.3s;
}

.bank-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.08);
}

.bank-logo {
  font-family: var(--font-serif);
  font-weight: 700;
  font-size: 1.5rem;
  color: #005096; /* BCA blue */
  margin-bottom: 20px;
}

.bank-logo.mandiri {
  color: #fdbb11; /* Mandiri gold/yellow */
  text-shadow: 1px 1px 1px #003063;
}

.account-name {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 5px;
}

.account-number {
  font-family: monospace;
  font-size: 1.3rem;
  letter-spacing: 2px;
  margin-bottom: 20px;
  color: #444;
}

.btn-copy {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: transparent;
  border: 1px solid #ccc;
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
  cursor: pointer;
  color: #555;
  transition: all 0.2s;
}

.btn-copy:hover {
  background: #f5f5f5;
  border-color: #999;
  color: #222;
}
</style>
