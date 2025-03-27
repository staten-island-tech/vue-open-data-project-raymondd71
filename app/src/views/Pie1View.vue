<template>
  <div class="flex justify-around">
    <PieChart class="w-[40%]" :key="chartKey5" :data="chartData1" />
  </div>
</template>

<script setup>
import PieChart from '@/components/PieChart.vue'
import { reactive, onMounted, computed } from 'vue'

const chartData1 = reactive({
  labels: ['Total Takers', 'Brooklyn', 'Queens', 'Bronx', 'Manhattan'],
  datasets: [
    {
      data: fiveData,
      backgroundColor: ['#36A2EB', '#FF6384', '#4BC0C0', '#FFA726', '#BF53FF'],
    },
  ],
})
</script>

<style scoped></style>
