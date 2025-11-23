<template>
  <section class="py-16 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
        <div v-for="area in areas" :key="area.title" class="bg-white p-8 rounded-2xl shadow-sm hover:shadow-md transition-shadow">
          <div class="w-12 h-12 bg-[#062b1f] rounded-lg flex items-center justify-center mb-6">
            <span class="text-2xl">{{ area.icon }}</span>
          </div>
          
          <h3 class="text-2xl font-serif text-[#062b1f] mb-4">{{ area.title }}</h3>
          <p class="text-gray-600 leading-relaxed mb-6">
            {{ area.description }}
          </p>
          
          <ul class="space-y-2">
            <li v-for="item in area.points" :key="item" class="flex items-start text-sm text-gray-500">
              <span class="mr-2 text-[#1FA34A]">•</span>
              {{ item }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const areas = [
  {
    title: 'Neuro-analytics',
    icon: '🧠',
    description: 'Analyzing neural patterns to understand subconscious decision-making processes.',
    points: [
      'Subconscious mapping',
      'Cognitive load analysis',
      'Emotional trigger identification'
    ]
  },
  {
    title: 'Digital Phenotyping',
    icon: '📱',
    description: 'Turning digital footprints into comprehensive behavioral profiles.',
    points: [
      'Social media sentiment',
      'Interaction pattern recognition',
      'Lifestyle correlation'
    ]
  },
  {
    title: 'Social Engineering',
    icon: '🌐',
    description: 'Designing environments and narratives that guide population behavior.',
    points: [
      'Narrative construction',
      'Group dynamics modeling',
      'Viral loop optimization'
    ]
  },
  {
    title: 'Predictive Psychometrics',
    icon: '📊',
    description: 'Forecasting individual and group actions based on psychological traits.',
    points: [
      'Personality trait scoring',
      'Behavioral forecasting',
      'Risk assessment'
    ]
  }
]
</script>
