<template>
  <section class="terms-section">
    <div class="terms-card">
      <h2>Warunki i Regulamin Programu</h2>
      <p class="instruction-text">
        Przeczytaj cały regulamin, aby móc kontynuować rejestrację.
      </p>

      <!-- Scrollable Container -->
      <div class="terms-box" @scroll="handleScroll">
        <h3>1. Postanowienia ogólne</h3>
        <p>
          Niniejszy regulamin określa zasady uczestnictwa w programie Ambasadorskim Lavish Care.
          Dołączenie do programu jest dobrowolne i wymaga zaakceptowania wszystkich poniższych punktów.
        </p>

        <h3>2. Wymagania wobec Ambasadora</h3>
        <p>
          Ambasador zobowiązuje się do promowania marki Lavish Care w sposób rzetelny, estetyczny i zgodny z wartościami marki.
          Wszelkie treści publikowane w mediach społecznościowych powinny być wysokiej jakości.
        </p>

        <h3>3. Poufność i Prawa Autorskie</h3>
        <p>
          Materiały przekazane przez markę są przeznaczone wyłącznie do celów promocyjnych.
          Tworzone przez Ambasadora treści mogą być udostępniane na oficjalnych profilach Lavish Care.
        </p>

        <h3>4. Ochrona Danych Osobowych (RODO)</h3>
        <p>
          Wyrażam zgodę na przetwarzanie moich danych osobowych w celu realizacji zgłoszenia oraz dalszej współpracy w ramach programu Ambasadorskiego.
        </p>
      </div>

      <!-- Scroll Indicator Badge -->
      <div v-if="!hasReadToBottom" class="scroll-warning">
        ↓ Przewiń na sam dół, aby odblokować akceptację
      </div>

      <!-- Checkbox (Disabled μέχρι να γίνει full scroll) -->
      <div class="checkbox-wrapper" :class="{ disabled: !hasReadToBottom }">
        <label class="custom-checkbox">
          <input
            type="checkbox"
            :disabled="!hasReadToBottom"
            v-model="isAccepted"
            @change="emitAcceptance"
          />
          <span class="checkmark"></span>
          <span class="label-text">
            Przeczytałem/am i akceptuję regulamin oraz warunki współpracy.
          </span>
        </label>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// Define emits για ενημέρωση του App.vue
const emit = defineEmits<{
  (e: 'terms-accepted', accepted: boolean): void
}>()

const hasReadToBottom = ref(false)
const isAccepted = ref(false)

// Έλεγχος αν ο χρήστης έφτασε στο τέρμα του scroll
const handleScroll = (event: Event) => {
  const target = event.target as HTMLElement
  // Tolerance 5px για μικροαποκλίσεις στο scroll
  const isAtBottom = target.scrollHeight - target.scrollTop <= target.clientHeight + 5

  if (isAtBottom) {
    hasReadToBottom.value = true
  }
}

const emitAcceptance = () => {
  emit('terms-accepted', isAccepted.value)
}
</script>

<style scoped>
.terms-section {
  max-width: 800px;
  margin: 40px auto;
  padding: 0 20px;
}

.terms-card {
  background: #1a1a1a;
  border: 1px solid rgba(197, 160, 89, 0.3);
  border-radius: 12px;
  padding: 30px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

h2 {
  color: #ffffff;
  margin-top: 0;
  font-size: 1.5rem;
}

.instruction-text {
  color: #a0a0a0;
  font-size: 0.9rem;
  margin-bottom: 20px;
}

/* Scroll Box */
.terms-box {
  height: 220px;
  overflow-y: auto;
  background: #121212;
  border: 1px solid #333333;
  border-radius: 8px;
  padding: 20px;
  color: #d0d0d0;
  font-size: 0.9rem;
  line-height: 1.6;
}

.terms-box h3 {
  color: #c5a059;
  font-size: 1rem;
  margin-top: 15px;
}

.terms-box h3:first-child {
  margin-top: 0;
}

/* Custom Scrollbar */
.terms-box::-webkit-scrollbar {
  width: 6px;
}
.terms-box::-webkit-scrollbar-thumb {
  background: #c5a059;
  border-radius: 4px;
}

/* Scroll Warning */
.scroll-warning {
  color: #c5a059;
  font-size: 0.8rem;
  text-align: center;
  margin-top: 10px;
  font-weight: 600;
}

/* Checkbox Styling */
.checkbox-wrapper {
  margin-top: 20px;
  transition: opacity 0.3s ease;
}

.checkbox-wrapper.disabled {
  opacity: 0.4;
  cursor: not-allowed;
}

.custom-checkbox {
  display: flex;
  align-items: center;
  gap: 12px;
  cursor: pointer;
  color: #ffffff;
  font-size: 0.95rem;
}

.custom-checkbox input {
  width: 18px;
  height: 18px;
  accent-color: #c5a059;
  cursor: pointer;
}

.custom-checkbox input:disabled {
  cursor: not-allowed;
}
</style>