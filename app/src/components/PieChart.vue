<template>
  <div></div>
</template>

<script setup>
import { Pie } from 'vue-chartjs'
import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js'
ChartJS.register(ArcElement, Tooltip, Legend)
const props = defineProps({
  data: Object,
})
const chartOptions = {
  responseive: true,
}
</script>

<style scoped></style>
