<template>
  <p class="text-center w-full my-6 text-2xl font-bold underline text-gray-700">
    Basic Accordion
  </p>
  <accordion />
  <p class="text-center w-full my-6 text-2xl font-bold underline text-gray-700">
    Accordion with Close Option
  </p>
  <accordionOption />
</template>
<script setup>
import accordion from "./components/accordion.vue";
import accordionOption from "./components/accordionOption.vue";
</script>
