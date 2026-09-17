<script setup lang="ts">
import Header from './components/Header.vue'
import Body from './components/Body.vue';
</script>

<template>
  <Header/>
  <Body/>
</template>

<style>

/* Reset για να κολλάει ο header στις άκρες της οθόνης */
html, body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #121212; /* Αποφεύγει λευκές αναλαμπές */
}

</style>