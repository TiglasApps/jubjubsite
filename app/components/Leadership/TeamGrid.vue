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
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const team = [
  {
    name: 'Dr. Marco Ferretti',
    role: 'Chief Executive Officer',
    image: 'https://images.unsplash.com/photo-1560250097-0b93528c311a?q=80&w=2574&auto=format&fit=crop',
    bio: 'Visionary leader with expertise in behavioral science and data analytics. Drives strategic direction and oversees all operations.'
  },
  {
    name: 'Dr. Sarah Mitchell',
    role: 'Head of Behavioral Psychology',
    image: 'https://images.unsplash.com/photo-1580489944761-15a19d654956?q=80&w=2574&auto=format&fit=crop',
    bio: 'Leading expert in psychographic profiling and cognitive pattern analysis. Develops advanced behavioral classification systems.'
  },
  {
    name: 'Alex Rivera',
    role: 'Lead Developer',
    image: 'https://images.unsplash.com/photo-1578632767115-351597cf2477?q=80&w=2574&auto=format&fit=crop',
    bio: 'Full-stack developer specializing in AI systems and data infrastructure. Architect of Node and core platform technologies.'
  },
  {
    name: 'Dr. Luca Moretti',
    role: 'Director of Data Science',
    image: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?q=80&w=2574&auto=format&fit=crop',
    bio: 'Expert in machine learning and predictive modeling. Leads development of behavioral prediction algorithms and cluster analysis.'
  }
]
</script>
