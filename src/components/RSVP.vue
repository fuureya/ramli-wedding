<script setup>
import { ref } from 'vue'

const formData = ref({
  name: '',
  guests: '',
  attending: 'yes'
})

const submitRSVP = () => {
  // Mock submission
  alert(`Thank you ${formData.value.name}! Your RSVP has been received.`)
  formData.value = { name: '', guests: '', attending: 'yes' }
}
</script>

<template>
  <section class="rsvp-section" id="rsvp">
    <div class="rsvp-container">
      <h2 class="section-title">RSVP</h2>
      <p class="rsvp-subtitle">Please let us know if you will be joining us. We kindly request your response by November 1, 2026.</p>
      
      <form @submit.prevent="submitRSVP" class="rsvp-form mt-4">
        <div class="form-group">
          <input type="text" v-model="formData.name" placeholder="Full Name" required />
        </div>
        
        <div class="form-group">
          <input type="number" v-model="formData.guests" placeholder="Number of Guests" min="1" max="10" required />
        </div>
        
        <div class="radio-group mt-4">
          <label class="radio-label">
            <input type="radio" v-model="formData.attending" value="yes" />
            <span class="custom-radio"></span>
            Joyfully Accepts
          </label>
          <label class="radio-label">
            <input type="radio" v-model="formData.attending" value="no" />
            <span class="custom-radio"></span>
            Regretfully Declines
          </label>
        </div>
        
        <button type="submit" class="btn-primary mt-8 w-100">RSVP NOW</button>
      </form>
    </div>
  </section>
</template>

<style scoped>
.rsvp-section {
  padding: 80px 20px;
  background-image: url('https://images.unsplash.com/photo-1520854221256-17451cc331bf?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80'); /* Soft floral or textured background */
  background-size: cover;
  background-position: center;
  position: relative;
}

.rsvp-section::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(249, 246, 243, 0.85); /* Frosty overlay */
}

.rsvp-container {
  position: relative;
  max-width: 500px;
  margin: 0 auto;
  background: var(--color-white);
  padding: 50px 40px;
  border-radius: var(--border-radius);
  box-shadow: 0 15px 40px rgba(0,0,0,0.08);
  text-align: center;
  z-index: 2;
}

.rsvp-subtitle {
  font-size: 0.95rem;
  color: #666;
  margin-top: 15px;
  margin-bottom: 30px;
}

.form-group {
  margin-bottom: 20px;
}

input[type="text"],
input[type="number"] {
  width: 100%;
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-family: var(--font-sans);
  font-size: 1rem;
  transition: border-color var(--transition-speed);
  background: transparent;
}

input[type="text"]:focus,
input[type="number"]:focus {
  outline: none;
  border-color: var(--color-primary);
}

.radio-group {
  display: flex;
  justify-content: space-around;
  gap: 15px;
}

.radio-label {
  display: flex;
  align-items: center;
  cursor: pointer;
  font-size: 0.95rem;
  color: #555;
  position: relative;
}

.radio-label input {
  opacity: 0;
  position: absolute;
}

.custom-radio {
  width: 20px;
  height: 20px;
  border: 2px solid #ddd;
  border-radius: 50%;
  margin-right: 10px;
  display: inline-block;
  position: relative;
  transition: all var(--transition-speed);
}

.radio-label input:checked + .custom-radio {
  border-color: var(--color-primary);
}

.radio-label input:checked + .custom-radio::after {
  content: '';
  width: 10px;
  height: 10px;
  background: var(--color-primary);
  border-radius: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.w-100 {
  width: 100%;
}

@media (max-width: 480px) {
  .radio-group {
    flex-direction: column;
    align-items: flex-start;
  }
  .rsvp-container {
    padding: 30px 20px;
  }
}
</style>
