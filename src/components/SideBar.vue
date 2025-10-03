<script setup lang="ts">
import Progessbar from './Progessbar.vue';
import CustomScrollbar from "./CustomScrollBar.vue"

</script>

<template>
  <!-- <CustomScrollbar> -->
  <div class="fixed left-0 top-0 w-76 h-screen  bg-white shadow-md rounded-lg overflow-y-auto">
    <!-- Profile Section -->
    <CustomScrollbar>
    <div class="flex flex-col items-center pt-[2rem] pb-[1rem]">
      <img
        src="../assets/myphoto_improved.png"
        alt="profile"
        class="w-40 h-35 object-scale-down rounded-[100%] shadow-md"
      />
      <h2 class="mt-4 text-lg font-semibold">Saroj Rai</h2>
      <p class="text-gray-500 text-sm">Fullstack Developer</p>

      <!-- Social Links -->
      <div class="flex gap-4 mt-4 text-[#C0392B]">
        <a target="__" href="https://www.facebook.com/saroj.rai.142/">
        <i class="fab fa-facebook">
        </i>
        </a>
        <a target="__" href="https://www.linkedin.com/in/saroj-rai-/">
        <i class="fab fa-linkedin">
        </i>
        </a>
        <a target="__" href="https://github.com/raikanxa">
        <i class="fab fa-github">
        </i>
        </a>
      </div>
    </div>
        
    <hr class="bg-[whitesmoke] mb-4 mx-4 h-[2px] border-none"/>
        
    <!-- Info -->
    <div class="px-6 text-sm space-y-2">
      <div class="flex justify-between">
        <span class="bg-[#C0392B] pl-1 pr-2 font-medium">Age:</span>
        <span>27</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] pl-1 pr-2 font-medium">Residence:</span>
        <span>NP</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] pl-1 pr-2 font-medium">Freelance:</span>
        <span class="text-green-500">Available</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] pl-1 pr-2 font-medium">Address:</span>
        <span class="text-right">Kathmandu, Nepal</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] pl-1 pr-2 font-medium">Email:</span>
        <span class="text-right">raisaroz88@gmail.com</span>
      </div>
      <div class="flex justify-between">
        <span class="bg-[#C0392B] pl-1 pr-2 font-medium">Phone no.:</span>
        <span class="text-right">+977 9860793854</span>
      </div>
    </div>

    <hr class="bg-[whitesmoke] mt-4 mx-4 h-[2px] border-none"/>

    <!-- Languages -->
    <div class="px-6 space-y-2">
      <h3 class="font-semibold mb-2">Languages</h3>
      <Progessbar label="Nepali" :value="100" />
      <Progessbar label="English" :value="100" />
      <Progessbar label="Indian" :value="60" />
    </div>

    <hr class="bg-[whitesmoke] mt-4 mx-4 h-[2px] border-none"/>

    <!-- Skills -->
    <div class="px-6 space-y-2">
      <h3 class="font-semibold mb-2">Skills</h3>
      <Progessbar label="HTML" :value="90" />
      <Progessbar label="CSS" :value="85" />
      <Progessbar label="JS" :value="80" />
      <Progessbar label="Python" :value="80" />
      <!-- <Progessbar label="WordPress" :value="85" /> -->
    </div>

    <hr class="bg-[whitesmoke] mt-4 mx-4 h-[2px] border-none"/>

    <!-- Extra Skills -->
    <div class="px-6 space-y-2">
      <h3 class="font-semibold mb-2">Extra Skills</h3>
      <div class="list-disc list-inside text-gray-600 text-sm text-gray-500">
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          Django, Django REST</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          JQuery, VueJS</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          PostgreSQL, MySQL</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          SQLite, Redis</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          Docker, Git</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          Nginx, Gunicorn, Celery</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          AWS, EC2</div>
        <div class="flex items-center gap-2">
          <img class="w-[18px] h-[18px]" src="../assets/sidebar/point.png"/>
          REST, SOAP</div>
      </div>
    </div>

    <!-- CV Button -->
    <div class="px-6 py-6">
      <a target="__" href="/public/CV.pdf" download>
      <button
        class="w-full bg-[#C0392B] text-black font-semibold py-2 rounded flex items-center justify-center gap-2 hover:bg-[#2C3E50] hover:text-white transition"
      >
        <span>Download CV</span>
        <i class="fas fa-download"></i>
      </button>
      </a>
    </div>
    </CustomScrollbar>
    </div>
    <!-- </CustomScrollbar> -->
</template>

<style scoped>
</style>