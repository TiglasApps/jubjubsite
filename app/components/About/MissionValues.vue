<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <!-- Mission -->
      <div class="text-center mb-20">
        <h2 class="text-3xl font-serif text-[#062b1f] mb-6">Our Mission</h2>
        <p class="text-xl md:text-2xl text-gray-600 max-w-4xl mx-auto leading-relaxed">
          To map the human mind at scale, providing actionable insights that drive behavior and shape the future of targeted engagement.
        </p>
      </div>

      <!-- Values -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
        <div v-for="value in values" :key="value.title" class="text-center">
          <div class="w-20 h-20 bg-[#062b1f]/5 rounded-full flex items-center justify-center mx-auto mb-6">
            <span class="text-4xl">{{ value.icon }}</span>
          </div>
          <h3 class="text-xl font-bold text-[#062b1f] mb-4">{{ value.title }}</h3>
          <p class="text-gray-600 leading-relaxed">
            {{ value.description }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const values = [
  {
    title: 'Precision',
    icon: '🎯',
    description: 'We operate with surgical accuracy, targeting specific psychographic profiles with tailored messaging.'
  },
  {
    title: 'Insight',
    icon: '👁️',
    description: 'We look beyond the surface, uncovering the hidden motivators that drive human action.'
  },
  {
    title: 'Influence',
    icon: '⚡',
    description: 'We don\'t just observe; we empower our partners to shape outcomes through data-driven strategies.'
  }
]
</script>
