<template>
  <div class="min-h-screen bg-[#062b1f] text-white relative">
    <!-- Navbar -->
    <header
  :class="[
    'fixed top-0 left-0 w-full z-50 transition-all duration-300',
    scrolled ? 'bg-white text-black shadow-lg' : 'bg-transparent text-white'
  ]"
  class="backdrop-blur-sm"
>
  <nav class="max-w-7xl mx-auto flex items-center justify-between py-5 px-6">
    <NuxtLink to="/" class="text-2xl font-bold hover:opacity-80 transition-opacity">Calico</NuxtLink>

    <!-- DESKTOP MENU -->
    <ul class="hidden md:flex gap-8 text-lg font-medium">
      <NuxtLink to="/research" class="cursor-pointer hover:opacity-70 transition-opacity">Research & Technology</NuxtLink>
      <NuxtLink to="/projects-development" class="cursor-pointer hover:opacity-70 transition-opacity">Projects</NuxtLink>
      <NuxtLink to="/partnering" class="cursor-pointer hover:opacity-70 transition-opacity">Partnering</NuxtLink>
      <NuxtLink to="/leadership" class="cursor-pointer hover:opacity-70 transition-opacity">Leadership</NuxtLink>
      <NuxtLink to="/careers" class="cursor-pointer hover:opacity-70 transition-opacity">Careers</NuxtLink>
    </ul>

    <!-- MOBILE ICON -->
    <div
      class="md:hidden text-3xl cursor-pointer"
      @click="mobileOpen = !mobileOpen"
    >
      ☰
    </div>
  </nav>

  <!-- MOBILE DROPDOWN -->
  <transition name="fade">
    <div
      v-if="mobileOpen"
      class="md:hidden bg-white text-black shadow-xl px-6 py-4 space-y-4 text-lg font-medium flex flex-col"
    >
      <NuxtLink to="/research" class="cursor-pointer hover:opacity-70" @click="mobileOpen = false">Research & Technology</NuxtLink>
      <NuxtLink to="/projects-development" class="cursor-pointer hover:opacity-70" @click="mobileOpen = false">Projects</NuxtLink>
      <NuxtLink to="/partnering" class="cursor-pointer hover:opacity-70" @click="mobileOpen = false">Partnering</NuxtLink>
      <NuxtLink to="/leadership" class="cursor-pointer hover:opacity-70" @click="mobileOpen = false">Leadership</NuxtLink>
      <NuxtLink to="/careers" class="cursor-pointer hover:opacity-70" @click="mobileOpen = false">Careers</NuxtLink>
    </div>
  </transition>
</header>


    
    <slot />
    <Footer />
    
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)
const mobileOpen = ref(false)



onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))

const handleScroll = () => {
  scrolled.value = window.scrollY > 80
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})


</script>

<style>
body {
  margin: 0;
  font-family: 'Inter', sans-serif;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

