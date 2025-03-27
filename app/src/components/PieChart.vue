<script setup>
import { reactive } from 'vue'
import { Pie } from 'vue-chartjs'
import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js'

ChartJS.register(ArcElement, Tooltip, Legend)

const props = defineProps({
  data: Object,
})

const chartOptions = reactive({
  responsive: true,
  plugins: {
    legend: {
      position: 'top',
    },
  },
})
</script>

<template>
  <div>
    <Pie class="mt-[2rem]" :data="props.data" :options="chartOptions" />
  </div>
</template>