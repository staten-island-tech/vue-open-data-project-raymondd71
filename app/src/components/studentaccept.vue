<template>
  <div>
    <h2>School Name: {{ students.feeder_school_name }}</h2>
    <h3>Number of Offers: {{ students.number_of_offers }}</h3>
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
