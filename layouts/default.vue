<template>
  <div class="flex flex-col min-h-screen">
    <!-- Header -->
    <header class="bg-green-400 border-b-2 border-gray-400">
      <div class="flex items-center justify-between px-6 py-4">
        <!-- Logo -->
        <div class="flex items-center">
          <img :src="logo" alt="Logo" class="w-12 h-12" />
        </div>

        <!-- Бургер-меню и навигация -->
        <div class="block max-sm:hidden">
          <nav class="flex gap-x-6">
            <NuxtLink to="/" class="hover:underline">Home</NuxtLink>
            <div class="relative">
              <button @click="toggleLabs" class="hover:underline">Labs</button>
              <div v-show="labsOpen" class="absolute bg-white shadow-md mt-1 flex flex-col p-2 rounded z-50">
                <NuxtLink to="/lab4" class="hover:underline">Lab4</NuxtLink>
                <NuxtLink to="/lab5" class="hover:underline">Lab5</NuxtLink>
                <NuxtLink to="/lab6" class="hover:underline">Lab6</NuxtLink>
              </div>
            </div>
            <NuxtLink to="/login" class="hover:underline">Login</NuxtLink>
            <NuxtLink to="/logout" class="hover:underline">Logout</NuxtLink>
          </nav>
        </div>

        <!-- Иконка бургера -->
        <div class="sm:hidden" @click="switchBurger">
          <span v-if="!burger" class="text-3xl cursor-pointer">☰</span>
          <span v-else class="text-3xl cursor-pointer">✖</span>
        </div>
      </div>

      <!-- Мобильное меню -->
      <div v-show="burger" class="sm:hidden flex flex-col items-start px-6 pb-4 gap-y-2 animate-fade-in">
        <NuxtLink to="/" class="hover:underline">Home</NuxtLink>
        <button @click="toggleLabs" class="hover:underline">Labs</button>
        <div v-show="labsOpen" class="pl-4 flex flex-col gap-y-1">
          <NuxtLink to="/lab4" class="hover:underline">Lab4</NuxtLink>
          <NuxtLink to="/lab5" class="hover:underline">Lab5</NuxtLink>
          <NuxtLink to="/lab6" class="hover:underline">Lab6</NuxtLink>
        </div>
        <NuxtLink to="/login" class="hover:underline">Login</NuxtLink>
        <NuxtLink to="/logout" class="hover:underline">Logout</NuxtLink>
      </div>
    </header>

    <!-- Main -->
    <main class="flex-grow p-5 bg-green-100">
      <slot />
    </main>

    <!-- Footer -->
    <footer class="bg-green-400 border-t-2 border-gray-400 flex justify-center gap-x-4 p-4">
      <a href="https://www.youtube.com/" target="_blank">
        <img src="@/assets/icons/youtube.svg" class="w-8 h-8" alt="YouTube" />
      </a>
      <a href="https://github.com/" target="_blank">
        <img src="@/assets/icons/github.svg" class="w-8 h-8" alt="GitHub" />
      </a>
      <a href="https://www.facebook.com/" target="_blank">
        <img src="@/assets/icons/facebook.svg" class="w-8 h-8" alt="Facebook" />
      </a>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import logo from '@/assets/l.png'

const burger = ref(false)
const labsOpen = ref(false)

const switchBurger = () => {
  burger.value = !burger.value
}
const toggleLabs = () => {
  labsOpen.value = !labsOpen.value
}
</script>

<style scoped>
@keyframes fade-in {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fade-in {
  animation: fade-in 0.3s ease-out;
}
</style>











