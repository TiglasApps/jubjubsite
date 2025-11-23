<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="text-center mb-16">
        <h2 class="text-3xl font-serif text-[#062b1f] mb-6">Active Operations</h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          We are deploying behavioral modification strategies across multiple domains to shape the future of human interaction.
        </p>
      </div>

      <div class="space-y-12">
        <!-- Pipeline Items -->
        <div v-for="phase in pipeline" :key="phase.phase" class="group">
          <div class="bg-gray-50 rounded-xl p-8 border border-gray-100 hover:shadow-md transition-shadow">
            
            <div class="flex flex-col md:flex-row md:items-center justify-between mb-6">
              <div>
                <h3 class="text-2xl font-bold text-[#062b1f] mb-2">{{ phase.phase }}</h3>
                <p class="text-gray-600">{{ phase.description }}</p>
              </div>
              <div class="mt-4 md:mt-0">
                <span class="px-4 py-2 bg-[#062b1f] text-white text-sm font-semibold rounded-full">
                  {{ phase.projects.length }} Active Projects
                </span>
              </div>
            </div>

            <!-- Projects Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div v-for="project in phase.projects" :key="project.name" class="bg-white p-4 rounded-lg border border-gray-200 flex justify-between items-center">
                <div>
                  <h4 class="font-bold text-[#062b1f]">{{ project.name }}</h4>
                  <p class="text-sm text-gray-500">{{ project.indication }}</p>
                </div>
                <span :class="{
                  'px-3 py-1 text-xs font-semibold rounded-full': true,
                  'bg-green-100 text-green-800': project.status === 'Active' || project.status === 'Live' || project.status === 'Complete',
                  'bg-yellow-100 text-yellow-800': project.status === 'Expanding' || project.status === 'Processing' || project.status === 'Testing'
                }">
                  {{ project.status }}
                </span>
              </div>
            </div>

            <!-- Progress Bar (Visual only) -->
            <div class="mt-8 relative h-2 bg-gray-200 rounded-full overflow-hidden">
               <div class="absolute top-0 left-0 h-full bg-[#1FA34A]" :style="{ width: getProgressWidth(phase.phase) }"></div>
            </div>

          </div>
        </div>
      </div>
      
      <div class="mt-12 text-center">
        <p class="text-sm text-gray-500">
          * Operational status as of Q4 2025. Clearance levels required for full project details.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const pipeline = [
  {
    phase: 'Data Collection',
    description: 'Aggregating massive datasets from digital footprints, IoT devices, and public records.',
    projects: [
      { name: 'Project Panopticon', status: 'Active', indication: 'Global Surveillance' },
      { name: 'Neural Harvest', status: 'Expanding', indication: 'Biometric Data' }
    ]
  },
  {
    phase: 'Pattern Recognition',
    description: 'Using AI to identify behavioral clusters and predict future actions.',
    projects: [
      { name: 'Cluster Alpha', status: 'Complete', indication: 'Voter Behavior' },
      { name: 'Deep Mind Map', status: 'Processing', indication: 'Consumer Trends' }
    ]
  },
  {
    phase: 'Strategy Formulation',
    description: 'Developing targeted interventions to nudge or shift population behavior.',
    projects: [
      { name: 'Nudge Protocol', status: 'Testing', indication: 'Social Engineering' },
      { name: 'Meme Vector', status: 'Active', indication: 'Viral Propagation' }
    ]
  },
  {
    phase: 'Deployment',
    description: 'Executing campaigns and monitoring real-time feedback loops.',
    projects: [
      { name: 'Operation Shift', status: 'Live', indication: 'Market Disruption' }
    ]
  }
]

const getProgressWidth = (phase: string) => {
  switch (phase) {
    case 'Data Collection': return '12.5%'
    case 'Pattern Recognition': return '37.5%'
    case 'Strategy Formulation': return '62.5%'
    case 'Deployment': return '87.5%'
    default: return '0%'
  }
}
</script>
