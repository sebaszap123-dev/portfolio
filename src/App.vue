<script setup lang="ts">
import { RouterView } from 'vue-router'
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <header class="fixed top-0 z-10 w-full shadow-lg">
    <nav class="flex items-center justify-between flex-wrap p-6 bg-nav">
      <div class="flex items-center flex-shrink-0 text-white mr-6">
        <span class="font-semibold text-xl tracking-tight">SebastiánFZ</span>
      </div>
      <div class="block lg:hidden">
        <button
          class="flex items-center px-3 py-2 border rounded text-teal-200 border-teal-400 hover:text-white hover:border-white"
          @click="toggleMenu"
        >
          <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div
        class="w-full lg:flex flex-grow lg:items-center lg:w-auto"
        :class="{ hidden: !isMenuOpen }"
      >
        <div class="text-lg lg:flex lg:grow lg:justify-center">
          <a
            href="#"
            class="block mt-4 lg:inline-block lg:mt-0 text-teal-200 hover:text-white mr-4"
          >
            Home
          </a>
          <a
            href="#"
            class="block mt-4 lg:inline-block lg:mt-0 text-teal-200 hover:text-white mr-4"
          >
            About
          </a>
          <a href="#" class="block mt-4 lg:inline-block lg:mt-0 text-teal-200 hover:text-white">
            Portfolio
          </a>
        </div>
        <div>
          <a
            href="#"
            class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0"
          >
            Support Me!
          </a>
        </div>
      </div>
    </nav>
  </header>
  <body>
    <RouterView />
  </body>
</template>

<style lang="css">
body {
  background-color: #243b4a;
}
.bg-nav {
  background-color: #2d4654;
}
</style>
