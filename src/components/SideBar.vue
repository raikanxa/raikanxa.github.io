<script setup lang="ts">
import Progessbar from './Progessbar.vue';
import CustomScrollbar from "./CustomScrollBar.vue"

</script>

<template>
  <!-- <CustomScrollbar> -->
  <div class="fixed left-0 top-0 w-76 h-screen  bg-white shadow-md rounded-lg overflow-y-auto">
    <!-- Profile Section -->
    <CustomScrollbar>
    <div class="flex flex-col items-center p-6">
      <img
        src="../assets/myphoto_improved.png"
        alt="profile"
        class="w-24 h-24 rounded-full border-4 border-white shadow-md"
      />
      <h2 class="mt-4 text-lg font-semibold">Saroj Rai</h2>
      <p class="text-gray-500 text-sm">Fullstack Developer</p>

      <!-- Social Links -->
      <div class="flex space-x-4 mt-4 text-[#C0392B]">
        <i class="fab fa-facebook"></i>
        <i class="fab fa-instagram"></i>
        <i class="fab fa-twitter"></i>
        <i class="fab fa-linkedin"></i>
        <i class="fab fa-github"></i>
        <i class="fas fa-globe"></i>
      </div>
    </div>

    <!-- Info -->
    <div class="px-6 text-sm space-y-2">
      <div class="flex justify-between">
        <span class="bg-[#C0392B] rounded-sm px-2 font-medium">Age:</span>
        <span>27</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] rounded-sm px-2 font-medium">Residence:</span>
        <span>NP</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] rounded-sm px-2 font-medium">Freelance:</span>
        <span class="text-green-500">Available</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] rounded-sm px-2 font-medium">Address:</span>
        <span class="text-right">Kathmandu, Nepal</span>
      </div>
    </div>

    <hr class="my-4" />

    <!-- Languages -->
    <div class="px-6 space-y-2">
      <h3 class="font-semibold mb-2">Languages</h3>
      <Progessbar label="Nepali" :value="100" />
      <Progessbar label="English" :value="100" />
      <Progessbar label="Indian" :value="60" />
    </div>

    <hr class="my-4" />

    <!-- Skills -->
    <div class="px-6 space-y-2">
      <h3 class="font-semibold mb-2">Skills</h3>
      <Progessbar label="HTML" :value="90" />
      <Progessbar label="CSS" :value="85" />
      <Progessbar label="JS" :value="80" />
      <Progessbar label="Python" :value="80" />
      <!-- <Progessbar label="WordPress" :value="85" /> -->
    </div>

    <hr class="my-4" />

    <!-- Extra Skills -->
    <div class="px-6 space-y-2">
      <h3 class="font-semibold mb-2">Extra Skills</h3>
      <ul class="list-disc list-inside text-gray-600 text-sm">
        <li>Django, Django REST</li>
        <li>JQuery, VueJS</li>
        <li>PostgreSQL, MySQL</li>
        <li>SQLite, Redis</li>
        <li>Docker, Git</li>
        <li>Nginx, Gunicorn, Celery</li>
        <li>AWS, EC2</li>
        <li>REST, SOAP</li>
      </ul>
    </div>

    <!-- CV Button -->
    <div class="px-6 py-6">
      <button
        class="w-full bg-[#C0392B] text-black font-semibold py-2 rounded flex items-center justify-center gap-2 hover:bg-[#2C3E50] hover:text-white transition"
      >
        <span>Download CV</span>
        <i class="fas fa-download"></i>
      </button>
    </div>
    </CustomScrollbar>
    </div>
    <!-- </CustomScrollbar> -->
</template>

<style scoped>
</style>