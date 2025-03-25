<template>
  <div>
    <h1 class="text-center m-auto mb-[1rem]">SAT Acceptance</h1>
    <div class="container flex flex-wrap w-[90%] justify-between m-auto">
      <sataccept
        v-for="(child, index) in childs"
        :key="child.school_name"
        :childs="child"
        :id="index"
      />
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
import sataccept from '@/components/sataccept.vue'
const childs = ref('')
async function childresult() {
  let res = await fetch('https://data.cityofnewyork.us/resource/f9bf-2cp4.json')
  let data = await res.json()
  childs.value = data
}

onMounted(() => {
  childresult()
})
</script>
