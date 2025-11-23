<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="member in team" :key="member.name" class="group">
          <div class="relative overflow-hidden rounded-xl mb-6">
            <img 
              :src="member.image" 
              :alt="member.name"
              class="w-full h-[400px] object-cover transition-transform duration-500 group-hover:scale-105"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-[#062b1f]/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
              <p class="text-white text-sm leading-relaxed">
                {{ member.bio }}
              </p>
            </div>
          </div>
          
          <h3 class="text-2xl font-serif text-[#062b1f] mb-1">{{ member.name }}</h3>
          <p class="text-[#1FA34A] font-medium tracking-wide uppercase text-sm mb-4">{{ member.role }}</p>
          
          <div class="flex space-x-4 opacity-60 hover:opacity-100 transition-opacity">
            <a href="#" class="text-[#062b1f] hover:text-[#1FA34A]">LinkedIn</a>
            <a href="#" class="text-[#062b1f] hover:text-[#1FA34A]">Twitter</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const team = [
  {
    name: 'Vitaly K.',
    role: 'Chief Architect',
    image: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?q=80&w=2574&auto=format&fit=crop',
    bio: 'A prodigy in cryptographic systems and neural networks. He speaks in code and dreams in algorithms. Rarely seen offline.'
  },
  {
    name: 'Arthur Sterling',
    role: 'Director of Global Operations',
    image: 'https://images.unsplash.com/photo-1560250097-0b93528c311a?q=80&w=2574&auto=format&fit=crop',
    bio: 'Former intelligence officer turned corporate strategist. He ensures our reach extends everywhere with ruthless efficiency.'
  },
  {
    name: 'Dr. Aiko Tanaka',
    role: 'Head of Behavioral Psychology',
    image: 'https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?q=80&w=2569&auto=format&fit=crop',
    bio: 'Specializes in subconscious influence and mass persuasion. Her methods are as elegant as they are effective.'
  },
  {
    name: 'James "Cipher" Wu',
    role: 'Lead Data Engineer',
    image: 'https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?q=80&w=2574&auto=format&fit=crop',
    bio: 'Architect of the "Panopticon" data lake. He ensures that no digital footprint goes unrecorded.'
  },
  {
    name: 'Eleanor Vance',
    role: 'VP of Strategic Narratives',
    image: 'https://images.unsplash.com/photo-1598550874175-4d7112ee7f38?q=80&w=2574&auto=format&fit=crop',
    bio: 'Master of public perception. She crafts the stories that shape societal truths.'
  },
  {
    name: 'Dr. Robert Kim',
    role: 'Head of Predictive Modeling',
    image: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?q=80&w=2574&auto=format&fit=crop',
    bio: 'Uses advanced statistics to forecast human behavior with terrifying accuracy.'
  }
]
</script>
