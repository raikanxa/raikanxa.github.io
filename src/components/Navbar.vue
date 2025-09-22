<template>
  <!-- <div class="flex flex-col items-center w-16 py-4 space-y-6 bg-white shadow-md h-[100%] max-h-[100%]"> -->
  <div class="fixed right-0 top-0 flex flex-col items-center w-16 py-4 space-y-6 bg-white shadow-md h-screen">
    <!-- Dark Mode Toggle -->
    <button
      class="flex items-center justify-center w-10 h-10 rounded-full hover:bg-gray-100"
      @click="$emit('toggle-theme')"
    >
      <img
      class="w-[50px] h-[35px]" 
      src="../assets/navbar/Contrast.png" 
      alt="Theme"
      />
    </button>

    <!-- Menu -->
    <nav class="flex flex-col items-center space-y-6">
      <div
        v-for="item in menu"
        :key="item.name"
        class="relative group"
      >
        <button
          @click="setActive(item.name)"
          :class="[
            'flex items-center justify-center w-12 h-12 rounded-full transition-all',
            active === item.name
              ? 'bg-red-500 text-black'
              : 'bg-gray-100 text-gray-600 hover:bg-gray-200'
          ]"
        >
          <i :class="item.icon"></i>
        </button>
        <!-- Tooltip -->
        <span
          class="absolute left-14 px-2 py-1 text-sm text-white bg-black rounded opacity-0 group-hover:opacity-100 transition-opacity"
        >
          {{ item.label }}
        </span>
      </div>
    </nav>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const active = ref("Home");

const menu = [
  { name: "Home", label: "Home", icon: "fas fa-home" },
  { name: "Services", label: "Services", icon: "fas fa-code" },
  { name: "Education", label: "Education", icon: "fas fa-graduation-cap" },
  { name: "Work", label: "Work", icon: "fas fa-briefcase" },
  // { name: "Chat", label: "Chat", icon: "fas fa-comment" }
];

const emit = defineEmits<{
  (e: 'scrollToSection', id: string): void
  (e: 'toggle-theme'): void
}>()


function setActive(name: string) {
  active.value = name;

  emit('scrollToSection', name);
}
</script>

<style scoped>
/* Optional: Smooth fade for tooltips */
.group span {
  top: 50%;
  transform: translateY(-50%);
  white-space: nowrap;
}
</style>
