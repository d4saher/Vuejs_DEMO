<template>
    <!-- Contingut del component -->
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Propietats reactives
  const data = ref(0);
  
  // Funcions computades, methods, etc.
  const computedData = computed(() => data.value * 2);
  
  function increment() {
    data.value++;
  }
  </script>
  
  <style>
    /* Estils del component */
  </style>
  