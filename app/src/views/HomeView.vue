<script setup>
import TheWelcome from '../components/TheWelcome.vue'

import { ref, onMounted } from 'vue'
const baby = ref('')
async function getinfant() {
  let res = await fetch('https://data.cityofnewyork.us/resource/fcau-jc6k.json')
  let data = await res.json()
  baby.value = data.results
}

onMounted(() => {
  getPokemon()
})
</script>
<template>
  <main>
    <TheWelcome />
  </main>
</template>
