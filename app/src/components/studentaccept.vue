<template>
  <div
    class="flex flex-col border-gray-300 border-[0.1rem] h-[8rem] rounded-lg p-4 text-center w-[30%]"
  >
    <h1>School Name: {{ students.feeder_school_name }}</h1>
    <h3 class="text-center">Number of Offers: {{ students.number_of_offers }}</h3>
    <h3>{{ id + 1 }}</h3>
    <br />
  </div>
</template>

<script setup>
const props = defineProps({
  students: Object,
  id: Number,
})
</script>

<style scoped></style>
