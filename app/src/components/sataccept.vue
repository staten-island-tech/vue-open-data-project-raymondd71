<template>
  <div
    class="flex flex-col border-black-300 border-[0.15rem] rounded-lg p-4 text-center w-[30%] mb-[1rem]"
  >
    <h1>School Name: {{ childs.school_name }}</h1>
    <h3 class="text-center">Number of Test taken: {{ childs.num_of_sat_test_takers }}</h3>
    <h3>Average Reading Score: {{ childs.sat_critical_reading_avg_score }}</h3>
    <h3>Average Math Score: {{ childs.sat_math_avg_score }}</h3>
    <h3>Average Writing Score: {{ childs.sat_writing_avg_score }}</h3>
  </div>
</template>

<script setup>
const props = defineProps({
  childs: Object,
  id: Number,
})
</script>

<style scoped></style>
