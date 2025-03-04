<template>
  <div class="container"></div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
const baby = ref('')
async function getinfant() {
  let res = await fetch('https://data.cityofnewyork.us/resource/fcau-jc6k.json')
  let data = await res.json()
  baby.value = data.results
}

onMounted(() => {
  getinfant()
})
</script>
