<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-12">
        <div>
          <h2 class="text-3xl font-serif text-[#062b1f] mb-4">Open Positions</h2>
          <p class="text-gray-600 max-w-xl">
            Join our team of scientists, engineers, and innovators working to solve the most important problem in biology.
          </p>
        </div>
        <div class="mt-6 md:mt-0">
          <button class="px-6 py-2 border border-gray-300 rounded-full text-gray-600 hover:border-[#1FA34A] hover:text-[#1FA34A] transition-colors">
            Filter by Department
          </button>
        </div>
      </div>

      <div class="space-y-4">
        <div v-for="job in jobs" :key="job.id" class="group bg-gray-50 hover:bg-white border border-transparent hover:border-gray-200 rounded-xl p-6 transition-all duration-300 hover:shadow-lg">
          <div class="flex flex-col md:flex-row justify-between items-start md:items-center">
            <div class="mb-4 md:mb-0">
              <span class="inline-block px-3 py-1 bg-[#1FA34A]/10 text-[#1FA34A] text-xs font-semibold tracking-wider uppercase rounded-full mb-3">
                {{ job.department }}
              </span>
              <h3 class="text-xl font-bold text-[#062b1f] group-hover:text-[#1FA34A] transition-colors">
                {{ job.title }}
              </h3>
              <div class="flex items-center mt-2 text-gray-500 text-sm">
                <span class="mr-4">📍 {{ job.location }}</span>
                <span>🕒 {{ job.type }}</span>
              </div>
            </div>
            
            <button class="px-6 py-2 bg-[#062b1f] text-white rounded-full opacity-0 group-hover:opacity-100 transform translate-x-4 group-hover:translate-x-0 transition-all duration-300">
              Apply Now
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const jobs = [
  {
    id: 1,
    title: 'Lead Data Scientist',
    department: 'Predictive Analytics',
    location: 'San Francisco, CA',
    type: 'Full-time'
  },
  {
    id: 2,
    title: 'Senior Psychological Profiler',
    department: 'Behavioral Science',
    location: 'London, UK',
    type: 'Full-time'
  },
  {
    id: 3,
    title: 'Memetic Engineer',
    department: 'Social Engineering',
    location: 'Remote',
    type: 'Contract'
  },
  {
    id: 4,
    title: 'Field Operations Director',
    department: 'Deployment',
    location: 'Washington, D.C.',
    type: 'Full-time'
  }
]
</script>
