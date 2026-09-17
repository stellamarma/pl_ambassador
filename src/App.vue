<script setup lang="ts">
import { ref } from 'vue'
import Header from './components/Header.vue'
import Body from './components/Body.vue'
import TermsSection from './components/TermsSection.vue'
import RegistrationForm from './components/RegistrationForm.vue'

// Κατάσταση για την ενεργοποίηση της φόρμας
const isTermsAccepted = ref(false)

const handleTermsAcceptance = (accepted: boolean) => {
  isTermsAccepted.value = accepted
}
</script>

<template>
  <Header />
  <main>
    <Body />
    <!-- Section για τους όρους χρήσης -->
    <TermsSection @terms-accepted="handleTermsAcceptance" />
    
    <!-- Η φόρμα ξεκλειδώνει όταν γίνουν αποδεκτοί οι όροι -->
    <RegistrationForm :is-enabled="isTermsAccepted" />
  </main>
</template>

<style>
/* Global reset */
* {
  box-sizing: border-box;
}

html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  overflow-x: hidden;
  background-color: #121212;
  font-family: system-ui, -apple-system, sans-serif;
  color: #ffffff;
}
</style>