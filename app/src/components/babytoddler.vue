<template>
  <div>
    <h2>{{ toddler.materal_race_or_ethnicity }}</h2>
    <h3>{{ toddler.year }}</h3>
    <h3>{{ id + 1 }}</h3>
    <br />
  </div>
</template>

<script setup>
const props = defineProps({
  toddler: Object,
  id: Number,
})
</script>

<style scoped></style>
