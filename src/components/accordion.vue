<template>
  <div class="w-full border">
    <button
      @click="toggleAcc"
      class="flex items-center w-full justify-between p-4 cursor-pointer border-gray-400 bg-gray-100"
    >
      <div class="flex items-center container">
        <span class="font-semibold">{{ title }}</span>
      </div>
      <svg
        class="h-6 w-6 transition-all duration-300"
        :class="isAccOpen ? 'rotate-180' : ''"
      >
        <path
          d="M10 18a.75.75 0 01-.53-.22l-6.25-6.25a.75.75 0 111.06-1.06L10 16.94l5.72-5.72a.75.75 0 111.06 1.06l-6.25 6.25a.75.75 0 01-.53.22z"
        />
      </svg>
    </button>
    <div v-if="isAccOpen" class="p-4">
      <p v-if="content">{{ content }}</p>
      <div v-else><slot name="content"></slot></div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const emit = defineEmits(["toggled"]);
const props = defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
  title: {
    type: String,
    default: "Title",
  },
  content: {
    type: String,
  },
});

let isAccOpen = ref(props.isOpen);

const toggleAcc = () => {
  emit("toggled", isAccOpen.value);
  isAccOpen.value = !isAccOpen.value;
};
</script>
