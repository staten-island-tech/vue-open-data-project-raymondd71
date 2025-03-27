<template>
  <div class="flex justify-around">
    <BarChart class="w-[40%]" :key="chartKey" :data="chartData" />
  </div>
</template>

<script setup>
import BarChart from '@/components/BarChart.vue'
import { reactive, onMounted, ref } from 'vue'
const students = ref('')
async function studentresult() {
  let res = await fetch('https://data.cityofnewyork.us/resource/k8ah-28f4.json')
  let data = await res.json()
  students.value = data
}

onMounted(() => {
  studentresult()
})
</script>

<style scoped></style>
