<template>
  <div class="flex justify-center">
    <div class="flex flex-col space-y-[20px]">
      <div
        class="flex bg-white rounded-[10px] px-[15px] py-[10px]"
        v-for="contact in allContacts"
      >
        <div
          class="
            flex
            items-center
            justify-center
            h-[50px]
            w-[50px]
            border border-blue-500
            rounded-full
            mr-3
          "
        >
          <h1 class="font-bold">{{ initials(contact) }}</h1>
          <!--          <slot>CT</slot>-->
          <!--          <slot>FB</slot>-->
          <!--          <slot name="initials" :myInitials="myInitials"></slot>-->
          <!--          <slot name="image"></slot>-->
          <!--          <h1 v-if="shouldShowImage">IMG</h1>-->
        </div>
        <div class="flex flex-col">
          <!--          <h1 class="font-bold">{{ name(contact) }}</h1>-->
          <h1 class="font-bold">{{ name(contact) }}</h1>
          <h3 class="text-gray-600">{{ contact.email }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, defineProps, ref } from "vue";

const props = defineProps({
  shouldShowImage: Boolean,
});

// const shouldShowImage = () => {
//   return props.shouldShowImage;
// };

const myInitials = ref("INT");

const allContacts = [
  {
    firstName: "Collins",
    lastName: "Too",
    email: "collinstoo.ct@gmail.com",
  },
  {
    firstName: "Albert",
    lastName: "Keen",
    email: "albert@gmail.com",
  },
];

const name = computed(() => {
  return (name) => {
    return name.firstName + " " + name.lastName;
  };
});

const initials = computed(() => {
  return (initials) => {
    if (!initials.firstName || !initials.lastName) return "";
    return initials.firstName[0] + initials.lastName[0];
  };
});
</script>

<style scoped></style>
