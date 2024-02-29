<template>
  <div class="container w-full mx-auto">
    <div v-for="(item, index) in items" :key="index">
      <div
        @click="toggle(index)"
        class="flex items-center justify-between p-4 cursor-pointer border-b border-gray-400 bg-gray-100 mb-2"
      >
        <div class="flex items-center container">
          <span class="font-semibold">{{ item.title }}</span>
        </div>
        <svg
          class="h-6 w-6 transition-transform"
          :class="{ rotate: Index === index }"
        >
          <path
            d="M10 18a.75.75 0 01-.53-.22l-6.25-6.25a.75.75 0 111.06-1.06L10 16.94l5.72-5.72a.75.75 0 111.06 1.06l-6.25 6.25a.75.75 0 01-.53.22z"
          />
        </svg>
      </div>
      <div v-if="Index === index" class="p-4">
        <p>{{ item.content }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const items = ref([
  {
    title: "Title",
    content:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
  },
  {
    title: "Title",
    content:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
  },
  {
    title: "Title",
    content:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
  },
]);

let Index = ref(null);

const toggle = (index) => {
  Index.value = Index.value === index ? null : index;
};
</script>

<style>
.rotate {
  transform: rotate(180deg);
}
</style>
