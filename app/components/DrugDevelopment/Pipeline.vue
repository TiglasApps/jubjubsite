<template>
  <section class="py-20 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] mb-6">Active Projects</h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Our cutting-edge systems for data aggregation, behavioral analysis, and predictive modeling are transforming how we understand and influence human behavior.
        </p>
      </div>

      <div class="space-y-8">
        <!-- Project Cards -->
        <div v-for="project in projects" :key="project.name" class="bg-gray-50 rounded-lg p-8 border border-gray-200 hover:shadow-lg transition-shadow">
          
          <div class="flex flex-col md:flex-row md:items-start justify-between mb-6">
            <div class="flex-1">
              <div class="flex items-center gap-4 mb-4">
                <h3 class="text-2xl md:text-3xl font-bold text-[#062b1f]">{{ project.name }}</h3>
                <span :class="{
                  'px-3 py-1 text-xs font-semibold rounded-full': true,
                  'bg-green-100 text-green-800': project.completion >= 70,
                  'bg-yellow-100 text-yellow-800': project.completion >= 40 && project.completion < 70,
                  'bg-blue-100 text-blue-800': project.completion < 40
                }">
                  {{ project.completion }}% Complete
                </span>
              </div>
              <p class="text-lg text-gray-700 leading-relaxed mb-4">
                {{ project.description }}
              </p>
            </div>
          </div>

          <!-- Key Features -->
          <div class="mb-6">
            <h4 class="text-sm font-semibold text-[#062b1f] uppercase tracking-wide mb-3">Key Capabilities</h4>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
              <div v-for="feature in project.features" :key="feature" class="flex items-start gap-2">
                <svg class="w-5 h-5 text-[#1FA34A] flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                </svg>
                <span class="text-gray-600">{{ feature }}</span>
              </div>
            </div>
          </div>

          <!-- Progress Bar -->
          <div class="mb-4">
            <div class="flex justify-between items-center mb-2">
              <span class="text-sm font-medium text-gray-700">Development Progress</span>
              <span class="text-sm font-bold text-[#062b1f]">{{ project.completion }}%</span>
            </div>
            <div class="relative h-3 bg-gray-200 rounded-full overflow-hidden">
              <div 
                class="absolute top-0 left-0 h-full bg-gradient-to-r from-[#062b1f] to-[#1FA34A] transition-all duration-500" 
                :style="{ width: project.completion + '%' }"
              ></div>
            </div>
          </div>

          <!-- Applications -->
          <div v-if="project.applications" class="mt-6 pt-6 border-t border-gray-200">
            <h4 class="text-sm font-semibold text-[#062b1f] uppercase tracking-wide mb-3">Applications</h4>
            <div class="flex flex-wrap gap-2">
              <span v-for="app in project.applications" :key="app" class="px-3 py-1 bg-white border border-gray-300 text-gray-700 text-sm rounded-full">
                {{ app }}
              </span>
            </div>
          </div>

        </div>
      </div>
      
      <div class="mt-16 text-center">
        <p class="text-sm text-gray-500">
          Project details updated as of Q4 2025. Full technical specifications available under NDA.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const projects = [
  {
    name: 'Node',
    completion: 100,
    description: 'A sophisticated infrastructure of interconnected servers and AI systems that continuously collect, aggregate, and analyze behavioral data. Node serves as the foundational data layer for all our operations, processing millions of data points daily through advanced psychological cluster analysis.',
    features: [
      'Distributed server architecture with global coverage',
      'Real-time data aggregation from multiple sources',
      'AI-powered psychological cluster identification',
      'Advanced pattern recognition algorithms',
      'Scalable processing of behavioral datasets',
      'Automated anomaly detection and flagging'
    ],
    applications: ['Data Infrastructure', 'Behavioral Analysis', 'Cluster Mapping', 'Predictive Modeling']
  },
  {
    name: 'JubJub',
    completion: 70,
    description: 'An advanced behavioral influence platform that leverages Node\'s data infrastructure to target and influence specific population segments and geographic territories. JubJub combines marketing objectives with predictive behavioral modeling to anticipate, shape, and induce future behaviors at scale.',
    features: [
      'Multi-segment targeting across demographics',
      'Geographic territory-based campaigns',
      'Predictive behavior modeling',
      'Real-time influence measurement',
      'Automated campaign optimization',
      'Future behavior induction protocols'
    ],
    applications: ['Marketing Campaigns', 'Behavior Prediction', 'Territory Influence', 'Trend Forecasting']
  },
  {
    name: 'Guignol',
    completion: 25,
    description: 'A comprehensive profiling system that creates detailed, anonymous yet highly personalized dossiers on online entities. Guignol performs deep psychological classification and predictive behavioral analysis, building complete behavioral profiles while maintaining operational anonymity.',
    features: [
      'Anonymous entity tracking and profiling',
      'Psychological classification algorithms',
      'Predictive behavioral modeling',
      'Cross-platform data synthesis',
      'Automated dossier generation',
      'Long-term behavior pattern analysis'
    ],
    applications: ['Entity Profiling', 'Psychological Classification', 'Behavior Prediction', 'Risk Assessment']
  }
]
</script>
