<template>
  <div class="container">
    <h1>Baby Death</h1>
    <babytoddler
      v-for="(toddler, index) in baby"
      :key="toddler.materal_race_or_ethnicity"
      :toddler="toddler"
      :id="index"
    />
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
import babytoddler from '@/components/babytoddler.vue'
const baby = ref('')
async function getinfant() {
  let res = await fetch('https://data.cityofnewyork.us/resource/fcau-jc6k.json')
  let data = await res.json()
  baby.value = data
}

onMounted(() => {
  getinfant()
})
</script>
