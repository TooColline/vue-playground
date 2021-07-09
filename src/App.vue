<template>
  <ContactDisplay :shouldShowImage="true">
    <template #initials="{ myInitials }"> {{ myInitials }} </template>
    <template #image> IMG </template>
  </ContactDisplay>
</template>

<script setup>
import ContactDisplay from "./components/ContactDisplay.vue";
import { ref } from "vue";

// const initials = ref("ME");
</script>

<style></style>
