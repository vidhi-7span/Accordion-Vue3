<template>
  <div class="w-full container mx-auto">
    <div v-for="(item, index) in Item" :key="index">
      <button
        @click="toggle(index)"
        class="flex justify-between items-center w-full py-4 px-6 border-b border-gray-400 bg-gray-100 mb-2"
      >
        <span class="font-semibold">{{ item.title }}</span>
        <svg
          :class="{ rotate: item.isOpen }"
          class="h-6 w-6 transition-transform"
        >
          <path
            d="M10 18a.75.75 0 01-.53-.22l-6.25-6.25a.75.75 0 111.06-1.06L10 16.94l5.72-5.72a.75.75 0 111.06 1.06l-6.25 6.25a.75.75 0 01-.53.22z"
          />
        </svg>
      </button>
      <div v-show="item.isOpen" class="p-6">
        {{ item.content }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const Item = ref([
  {
    title: "Title",
    content: "Description",
  },
  {
    title: "Title",
    content: "Description",
  },
  {
    title: "Title",
    content: "Description",
  },
]);

const toggle = (index) => {
  Item.value[index].isOpen = !Item.value[index].isOpen;
};
</script>

<style scoped>
.rotate {
  transform: rotate(180deg);
}
</style>
