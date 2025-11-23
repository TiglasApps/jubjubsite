<template>
  <section class="w-full flex justify-center py-24">
    <div class="w-[90%] max-w-[1400px] grid grid-cols-1 lg:grid-cols-2">

      <!-- LEFT SIDE - DARK TEXT PANEL -->
      <div class="bg-[#2B2B2B] text-white p-16 relative flex flex-col justify-center">

        <!-- Featured badge -->
        <div class="absolute -top-6 left-10 bg-[#1FA34A] text-white px-6 py-3 text-lg font-semibold">
          Core Methodology
        </div>

        <p class="text-gray-300 mb-6 text-lg">Established 2024</p>

        <h2 class="text-4xl font-serif mb-6 leading-snug">
          The Psychology of<br />
          Influence
        </h2>

        <p class="text-[19px] leading-relaxed text-gray-300 max-w-[85%]">
          Our journey began with a simple question: What drives human decision-making? By combining behavioral economics with massive data aggregation, we've unlocked the ability to predict and shape outcomes at scale. We don't just analyze data; we understand the people behind it.
        </p>
      </div>

      <!-- RIGHT SIDE - IMAGE -->
      <div>
        <img
          :src="image"
          alt="Behavioral Analysis"
          class="w-full h-full object-cover"
        />
      </div>

    </div>
  </section>
</template>

<script setup>
const image = 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=2670&auto=format&fit=crop' // Data/Psychology abstract
// Sostituisci con il file reale, es: '@/assets/Schermata 2025-11-17 alle 11.27.42.png'
</script>
