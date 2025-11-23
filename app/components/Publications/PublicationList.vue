<template>
  <section class="py-16 bg-white">
    <div class="max-w-4xl mx-auto px-4 md:px-6">
      <div class="mb-12">
        <h2 class="text-3xl font-serif text-[#062b1f] mb-4">Selected Publications</h2>
        <p class="text-gray-600">
          Our scientists regularly publish their findings in top-tier peer-reviewed journals.
        </p>
      </div>

      <div class="space-y-8">
        <div v-for="pub in publications" :key="pub.title" class="group border-b border-gray-100 pb-8 last:border-0">
          <div class="flex flex-col md:flex-row md:items-start justify-between">
            <div class="flex-1 pr-8">
              <h3 class="text-xl font-bold text-[#062b1f] mb-2 group-hover:text-[#1FA34A] transition-colors">
                {{ pub.title }}
              </h3>
              <p class="text-gray-600 mb-2 italic">
                {{ pub.authors }}
              </p>
              <div class="flex items-center text-sm text-gray-500">
                <span class="font-semibold text-[#062b1f] mr-2">{{ pub.journal }}</span>
                <span class="mr-2">•</span>
                <span>{{ pub.date }}</span>
              </div>
            </div>
            
            <div class="mt-4 md:mt-0 flex-shrink-0">
              <a 
                :href="pub.link" 
                target="_blank"
                class="inline-flex items-center px-4 py-2 border border-gray-200 rounded-lg text-sm font-medium text-gray-600 hover:border-[#1FA34A] hover:text-[#1FA34A] transition-colors"
              >
                Read Paper
                <span class="ml-2">↗</span>
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-12 text-center">
        <button class="px-8 py-3 bg-gray-100 text-[#062b1f] font-bold rounded-full hover:bg-gray-200 transition-colors">
          View All Publications
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const publications = [
  {
    title: 'The Algorithmic Self: Quantifying Identity in the Digital Age',
    authors: 'Thorne A, et al.',
    journal: 'Journal of Behavioral Data',
    date: '2025',
    link: '#'
  },
  {
    title: 'Predicting Riots: A Multi-Variable Analysis of Social Unrest',
    authors: 'Chen X, Smith M.',
    journal: 'Social Dynamics Review',
    date: '2024',
    link: '#'
  },
  {
    title: 'Consumer Trance States: Inducing Purchase Behavior via Micro-Targeting',
    authors: 'Vance J, et al.',
    journal: 'Neuro-Marketing Quarterly',
    date: '2024',
    link: '#'
  },
  {
    title: 'The End of Privacy: Implications for State Control',
    authors: 'Blackwood S.',
    journal: 'Global Security Journal',
    date: '2023',
    link: '#'
  }
]
</script>
