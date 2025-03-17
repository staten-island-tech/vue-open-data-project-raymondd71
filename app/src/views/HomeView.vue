<template>
  <div>
    <h1 class="text-center m-auto">SHSAT Acceptance</h1>
    <div class="container flex flex-wrap w-[90%] justify-between m-auto">
      <studentaccept
        v-for="(student, index) in students"
        :key="student.feeder_school_name"
        :students="student"
        :id="index"
      />
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
import studentaccept from '@/components/studentaccept.vue'
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
