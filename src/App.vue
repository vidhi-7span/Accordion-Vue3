<template>
  <div class="">
    <div
      v-for="(item, index) in items"
      :key="index"
      class="border-b border-gray-200"
    >
      <div
        @click="toggle(index)"
        class="flex items-center justify-between p-4 cursor-pointer"
      >
        <div class="flex items-center container">
          <span class="font-semibold">{{ item.title }}</span>
        </div>
        <svg
          class="h-6 w-6 transform transition-transform"
          :class="{ 'rotate-180': activeIndex === index }"
        >
          <path
            d="M10 18a.75.75 0 01-.53-.22l-6.25-6.25a.75.75 0 111.06-1.06L10 16.94l5.72-5.72a.75.75 0 111.06 1.06l-6.25 6.25a.75.75 0 01-.53.22z"
          />
        </svg>
      </div>
      <div v-if="activeIndex === index" class="p-4">
        <p>{{ item.content }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const items = ref([
  {
    title: " Item 1",
    content:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ",
  },
  {
    title: " Item 2",
    content:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ",
  },
  {
    title: " Item 3",
    content:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ",
  },
]);

let activeIndex = ref(null);

const toggle = (index) => {
  activeIndex.value = activeIndex.value === index ? null : index;
};
</script>

<style>
.rotate-180 {
  transform: rotate(180deg);
}
</style>
