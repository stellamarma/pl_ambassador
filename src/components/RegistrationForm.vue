<template>
  <section class="form-section">
    <div class="form-card" :class="{ disabled: !isEnabled }">
      <h2>Formularz Zgłoszeniowy</h2>
      <p v-if="!isEnabled" class="locked-notice">
        🔒 Musisz najpierw przeczytać i zaakceptować regulamin, aby wypełnić formularz.
      </p>

      <form @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="fullName">Imię i Nazwisko</label>
          <input
            id="fullName"
            type="text"
            v-model="formData.fullName"
            :disabled="!isEnabled"
            placeholder="np. Jan Kowalski"
            required
          />
        </div>

        <div class="form-group">
          <label for="email">Adres E-mail</label>
          <input
            id="email"
            type="email"
            v-model="formData.email"
            :disabled="!isEnabled"
            placeholder="np. jan@example.com"
            required
          />
        </div>

        <div class="form-group">
          <label for="social">Link do Social Media (Instagram / TikTok)</label>
          <input
            id="social"
            type="url"
            v-model="formData.social"
            :disabled="!isEnabled"
            placeholder="https://instagram.com/twój_profil"
            required
          />
        </div>

        <button type="submit" class="submit-btn" :disabled="!isEnabled">
          WYŚLIJ ZGŁOSZENIE
        </button>
      </form>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

defineProps<{
  isEnabled: boolean
}>()

const formData = reactive({
  fullName: '',
  email: '',
  social: ''
})

const handleSubmit = () => {
  alert('Dziękujemy za zgłoszenie! Skontaktujemy się z Tobą wkrótce.')
}
</script>

<style scoped>
.form-section {
  max-width: 800px;
  margin: 0 auto 60px auto;
  padding: 0 20px;
}

.form-card {
  background: #1a1a1a;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  padding: 30px;
  transition: all 0.3s ease;
}

.form-card.disabled {
  opacity: 0.5;
  pointer-events: none;
}

h2 {
  color: #ffffff;
  margin-top: 0;
  font-size: 1.5rem;
}

.locked-notice {
  color: #c5a059;
  background: rgba(197, 160, 89, 0.1);
  padding: 10px 15px;
  border-radius: 6px;
  font-size: 0.9rem;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 20px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

label {
  color: #e0e0e0;
  font-size: 0.9rem;
  font-weight: 500;
}

input {
  background: #121212;
  border: 1px solid #333333;
  border-radius: 6px;
  padding: 12px 15px;
  color: #ffffff;
  font-size: 0.95rem;
  outline: none;
  transition: border-color 0.3s ease;
}

input:focus {
  border-color: #c5a059;
}

.submit-btn {
  width: 100%;
  padding: 14px;
  background: #c5a059;
  color: #121212;
  border: none;
  border-radius: 6px;
  font-weight: 700;
  letter-spacing: 1px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.submit-btn:hover:not(:disabled) {
  background: #d4af66;
}

.submit-btn:disabled {
  background: #444444;
  color: #888888;
  cursor: not-allowed;
}
</style>