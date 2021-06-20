<template>
  <h1>Hello {{ myName }}</h1>
</template>

<script setup>
import { ref } from 'vue'

const myName = ref('Collins')

</script>

<style scoped>
h1 {
  @apply text-center;
}
</style>
