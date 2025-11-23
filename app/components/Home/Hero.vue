<template>
  <section class="relative flex items-center justify-center text-center h-screen px-6 overflow-hidden">
    
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 z-0">
      <img 
        src="https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2670&auto=format&fit=crop" 
        alt="Data Visualization Background" 
        class="w-full h-full object-cover opacity-40"
      />
      <div class="absolute inset-0 bg-gradient-to-b from-[#062b1f]/90 via-[#062b1f]/70 to-[#062b1f]"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 max-w-5xl mx-auto flex flex-col items-center">
      <h2 
        class="text-5xl md:text-7xl font-serif leading-tight mb-8 opacity-0 animate-fade-in-up"
        style="animation-delay: 0.2s;"
      >
        Decoding Human Behavior for Precision Impact
      </h2>
      
      <p 
        class="text-xl md:text-2xl text-gray-200 mb-10 max-w-3xl opacity-0 animate-fade-in-up"
        style="animation-delay: 0.4s;"
      >
        We aggregate data and leverage behavioral science to map personality traits and influence population dynamics.
      </p>

      <NuxtLink 
        to="/about"
        class="px-8 py-4 bg-white text-[#062b1f] font-semibold rounded-full hover:bg-gray-100 transition-all transform hover:scale-105 shadow-lg opacity-0 animate-fade-in-up inline-block"
        style="animation-delay: 0.6s;"
      >
        Explore Our Methodology
      </NuxtLink>
    </div>

  </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 1s ease-out forwards;
}
</style>