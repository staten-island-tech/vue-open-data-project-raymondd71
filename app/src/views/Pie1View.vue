<template>
  <div class="flex justify-around">
    <PieChart class="w-[40%]" :key="chartKey" :data="chartData1" />
  </div>
</template>

<script setup>
import PieChart from '@/components/PieChart.vue'
import { reactive, onMounted, ref } from 'vue'

const students = reactive([0, 0, 0])
const chartKey = ref(0)
async function studentresult() {
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
  studentresult()
})

const chartData1 = reactive({
  labels: ['Non-Test Takers', 'Rejected Test Takers', 'Accepted Test Takers'],
  datasets: [
    {
      data: students,
      backgroundColor: ['#36A2EB', '#FF6384', '#BF53FF'],
    },
  ],
})
</script>

<style scoped></style>
