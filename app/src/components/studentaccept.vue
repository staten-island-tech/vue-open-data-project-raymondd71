<template>
  <div
    class="flex flex-col border-black-300 border-[0.15rem] rounded-lg p-4 text-center w-[30%] mb-[1rem]"
  >
    <h1>School Name: {{ students.feeder_school_name }}</h1>
    <h3 class="text-center">Number of Offers: {{ students.number_of_offers }}</h3>
    <h3 v-if="students.count_of_testers === '0-5'">Number of People Taking: 5</h3>
    <h3 v-if="students.count_of_testers > 5">
      Number of People Taking: {{ students.count_of_testers }}
    </h3>
    <h3 v-if="students.number_of_offers === '0-5'">
      Number of Rejected:
      {{ students.count_of_testers - 5 }}
    </h3>
    <h3 v-else>
      Number of Rejected:
      {{ students.count_of_testers - students.number_of_offers }}
    </h3>
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
students.count_of_tester = parseInt(students.count_of_testers, 10) students.number_of_offers =
parseInt(students.number_of_offers, 10)
