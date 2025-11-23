<template>
  <section class="relative flex items-center justify-center text-center h-[50vh] min-h-[400px] px-6 overflow-hidden bg-[#062b1f]">
    
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 z-0">
      <img 
        v-if="backgroundImage"
        :src="backgroundImage" 
        alt="Header Background" 
        class="w-full h-full object-cover opacity-40"
      />
      <div class="absolute inset-0 bg-gradient-to-b from-[#062b1f]/80 via-[#062b1f]/60 to-[#062b1f]"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 max-w-4xl mx-auto flex flex-col items-center animate-fade-in-up">
      <h1 class="text-4xl md:text-6xl font-serif leading-tight mb-4 text-white">
        {{ title }}
      </h1>
      
      <p v-if="subtitle" class="text-lg md:text-xl text-gray-300 max-w-2xl">
        {{ subtitle }}
      </p>
    </div>

  </section>
</template>

<script setup lang="ts">
defineProps<{
  title: string;
  subtitle?: string;
  backgroundImage?: string;
}>();
</script>

<style scoped>
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}
</style>
