<template>
  <div class="flex justify-center">
    <div class="flex bg-white rounded-[10px] px-[15px] py-[10px]">
      <div class="flex items-center justify-center h-[50px] w-[50px] border border-blue-500 rounded-full mr-5">
        <h1>{{ initials }}</h1>
      </div>
      <div class="flex flex-col">
        <h1 class="font-bold"> {{ name }}</h1>
        <h3 class="text-gray-600">{{ myEmail }}</h3>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const firstName = ref('Collins')
const lastName = ref('Too')
const myEmail = ref('collinstoo.ct@gmail.com')

const name = computed(() => {
  return firstName.value + ' ' + lastName.value
})

const initials = computed(() => {
  if(!firstName.value || !lastName.value) return ''
  return firstName.value[0] + lastName.value[0]
})

</script>

<style scoped>
</style>
