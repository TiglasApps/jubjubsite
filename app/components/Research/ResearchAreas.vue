<template>
  <!-- Introduction Section -->
  <section class="py-16 bg-white">
    <div class="max-w-4xl mx-auto px-4 md:px-6 text-center">
      <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] mb-6">Our Research Mission</h2>
      <p class="text-lg text-gray-700 leading-relaxed mb-4">
        At JubJub Lab, we're pushing the boundaries of behavioral science and human cognition research. Our multidisciplinary approach combines neuroscience, data analytics, and psychology to unlock deeper understanding of how people think, decide, and act.
      </p>
      <p class="text-lg text-gray-700 leading-relaxed">
        Through rigorous scientific methodology and cutting-edge technology, we're building a comprehensive map of human behavior that can transform how we approach everything from healthcare to education.
      </p>
    </div>
  </section>

  <!-- Research Areas Grid -->
  <section class="py-16 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] text-center mb-12">Research Areas</h2>
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

  <!-- Projects Development CTA with Images -->
  <section class="relative py-20 bg-gray-900 overflow-hidden">
    <!-- Background Image Grid -->
    <div class="absolute inset-0 grid grid-cols-3 opacity-30">
      <div class="bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1507413245164-6160d8298b31?q=80&w=2670&auto=format&fit=crop')"></div>
      <div class="bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1532094349884-543bc11b234d?q=80&w=2670&auto=format&fit=crop')"></div>
      <div class="bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?q=80&w=2670&auto=format&fit=crop')"></div>
    </div>
    
    <!-- Overlay -->
    <div class="absolute inset-0 bg-gradient-to-br from-[#062b1f]/95 to-[#0a4d35]/95"></div>
    
    <!-- Content -->
    <div class="relative z-10 max-w-4xl mx-auto px-4 md:px-6 text-center text-white">
      <div class="w-20 h-20 bg-white/20 rounded-full flex items-center justify-center mx-auto mb-6">
        <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z"></path>
        </svg>
      </div>
      <h2 class="text-3xl md:text-4xl font-serif mb-4">Active Research Projects</h2>
      <p class="text-lg text-white/90 mb-8 max-w-2xl mx-auto">
        Explore our current research initiatives and development projects. From Node and JubJub to Guignol, discover the cutting-edge technologies we're building to advance behavioral science.
      </p>
      <NuxtLink 
        to="/projects-development" 
        class="inline-flex items-center gap-2 px-8 py-4 bg-white text-[#062b1f] font-semibold rounded-full hover:bg-gray-100 transition-colors shadow-lg hover:shadow-xl"
      >
        View All Projects
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path>
        </svg>
      </NuxtLink>
    </div>
  </section>

  <!-- Research Methodology -->
  <section class="py-16 bg-gradient-to-br from-[#062b1f] to-[#0a4d35] text-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <h2 class="text-3xl md:text-4xl font-serif text-center mb-12">Our Methodology</h2>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div v-for="step in methodology" :key="step.number" class="text-center">
          <div class="w-16 h-16 bg-white/20 rounded-full flex items-center justify-center mx-auto mb-4">
            <span class="text-2xl font-bold">{{ step.number }}</span>
          </div>
          <h3 class="text-xl font-bold mb-3">{{ step.title }}</h3>
          <p class="text-white/80 leading-relaxed">{{ step.description }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Publications CTA -->
  <section class="py-20 bg-white">
    <div class="max-w-4xl mx-auto px-4 md:px-6 text-center">
      <div class="bg-gradient-to-br from-gray-50 to-gray-100 rounded-2xl p-12 border border-gray-200">
        <div class="w-20 h-20 bg-[#062b1f] rounded-full flex items-center justify-center mx-auto mb-6">
          <svg class="w-10 h-10 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"></path>
          </svg>
        </div>
        <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] mb-4">Explore Our Publications</h2>
        <p class="text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
          Dive deeper into our research findings. Browse our collection of peer-reviewed papers, white papers, and research reports that detail our discoveries and methodologies.
        </p>
        <NuxtLink 
          to="/publications" 
          class="inline-flex items-center gap-2 px-8 py-4 bg-[#062b1f] text-white font-semibold rounded-full hover:bg-[#0a4d35] transition-colors shadow-lg hover:shadow-xl"
        >
          View Publications
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path>
          </svg>
        </NuxtLink>
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

const methodology = [
  {
    number: '1',
    title: 'Data Collection',
    description: 'Gather comprehensive behavioral data from multiple sources using ethical and transparent methods.'
  },
  {
    number: '2',
    title: 'Analysis & Modeling',
    description: 'Apply advanced statistical methods and machine learning to identify patterns and build predictive models.'
  },
  {
    number: '3',
    title: 'Validation & Publication',
    description: 'Rigorously test our findings and share results through peer-reviewed publications and open research.'
  }
]
</script>
