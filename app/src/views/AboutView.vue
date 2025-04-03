<script>
import { reactive, onMounted, ref } from 'vue'
import BarChart from '@/components/BarChart.vue'

const students = reactive([0, 0, 0])
const chartKey = ref(0)
async function results() {
  let res = await fetch('https://data.cityofnewyork.us/resource/k8ah-28f4.json')
  let data = await res.json()
  data.forEach((el) => {
    students[0] += parseInt(el.count_of_students_in_hs)
    if (el.count_of_testers === '0-5') {
      students[1] += 5
    } else {
      students[1] += parseInt(el.count_of_testers)
    }
    if (el.number_of_offers === '0-5') {
      students[2] += 5
    } else {
      students[2] += parseInt(el.number_of_offers)
    }
  })
  students[0] -= students[1]
  students[1] -= students[2]
  console.log(students)
  chartKey.value++
}

onMounted(() => {
  results()
})
const chartData = reactive({
  labels: ['Non-Test Takers', 'Rejected Test Takers', 'Accepted Test Takers'],
  datasets: [
    {
      label: 'Students',
      backgroundColor: '#42A5F5',
      data: students,
    },
  ],
})
</script>
<template>
  <BarChart :data="chartData" :key="chartKey" />
</template>
