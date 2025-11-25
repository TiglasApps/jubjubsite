<template>
  <div>
    <!-- Company Story -->
    <section class="py-20 bg-white">
      <div class="max-w-4xl mx-auto px-4 md:px-6">
        <div class="text-center mb-12">
          <h2 class="text-4xl font-serif text-[#062b1f] mb-8">Our Story</h2>
        </div>
        <div class="space-y-6 text-gray-700 leading-relaxed text-lg">
          <p class="text-center max-w-3xl mx-auto">
            JubJub Lab was founded on a revolutionary premise: that human behavior, when properly analyzed and understood at scale, becomes predictable and influenceable.
          </p>
          <p class="text-center max-w-3xl mx-auto">
            Our founding team of neuroscientists, data scientists, and behavioral psychologists recognized that traditional marketing and influence strategies were operating blindly. By combining advanced data aggregation, personality cluster analysis, and deep understanding of cognitive patterns, we created a system that maps the collective mind of populations.
          </p>
          <p class="text-center max-w-3xl mx-auto">
            Today, we stand at the intersection of neuroscience, big data, and behavioral economics—providing our partners with unprecedented insights into how people think, what drives their decisions, and how to shape outcomes in specific geographic and demographic areas.
          </p>
        </div>
      </div>
    </section>

    <!-- Visual Break: Image Grid -->
    <section class="py-0 bg-gray-900">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4">
        <div class="relative h-80 overflow-hidden group">
          <img 
            src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=2670&auto=format&fit=crop" 
            alt="Data Analysis" 
            class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-[#062b1f]/90 via-[#062b1f]/40 to-transparent flex items-end p-6">
            <h3 class="text-white text-xl font-bold">Data Analysis</h3>
          </div>
        </div>
        
        <div class="relative h-80 overflow-hidden group">
          <img 
            src="https://images.unsplash.com/photo-1559757175-5700dde675bc?q=80&w=2831&auto=format&fit=crop" 
            alt="Neuroscience" 
            class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-[#062b1f]/90 via-[#062b1f]/40 to-transparent flex items-end p-6">
            <h3 class="text-white text-xl font-bold">Neuroscience</h3>
          </div>
        </div>
        
        <div class="relative h-80 overflow-hidden group">
          <img 
            src="https://images.unsplash.com/photo-1582213782179-e0d53f98f2ca?q=80&w=2940&auto=format&fit=crop" 
            alt="Behavioral Insights" 
            class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-[#062b1f]/90 via-[#062b1f]/40 to-transparent flex items-end p-6">
            <h3 class="text-white text-xl font-bold">Behavioral Insights</h3>
          </div>
        </div>
        
        <div class="relative h-80 overflow-hidden group">
          <img 
            src="https://images.unsplash.com/photo-1518432031352-d6fc5c10da5a?q=80&w=2874&auto=format&fit=crop" 
            alt="Technology" 
            class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-[#062b1f]/90 via-[#062b1f]/40 to-transparent flex items-end p-6">
            <h3 class="text-white text-xl font-bold">Technology</h3>
          </div>
        </div>
      </div>
    </section>

    <!-- Mission -->
    <section class="relative py-32 bg-gradient-to-br from-[#062b1f] to-[#0a4d35] text-white overflow-hidden">
      <!-- Background Image -->
      <div class="absolute inset-0 z-0">
        <img 
          src="https://images.unsplash.com/photo-1576086213369-97a306d36557?q=80&w=2680&auto=format&fit=crop" 
          alt="Background" 
          class="w-full h-full object-cover opacity-20"
        />
      </div>
      
      <!-- Content -->
      <div class="relative z-10 max-w-6xl mx-auto px-4 md:px-6 text-center">
        <h2 class="text-3xl md:text-4xl font-serif mb-8">Our Mission</h2>
        <p class="text-xl md:text-2xl max-w-4xl mx-auto leading-relaxed text-white/80">
          To map the human mind at scale, providing actionable insights that drive behavior and shape outcomes through advanced psychographic profiling, data aggregation, and behavioral control strategies.
        </p>
      </div>
    </section>

    <!-- Core Values -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-6xl mx-auto px-4 md:px-6">
        <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] text-center mb-16">Our Core Values</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
          <div v-for="value in values" :key="value.title" class="bg-white p-8 rounded-lg shadow-md hover:shadow-xl transition-shadow">
            <div class="w-16 h-16 bg-[#062b1f] rounded-lg flex items-center justify-center mb-6">
              <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" v-html="value.icon"></svg>
            </div>
            <h3 class="text-xl font-bold text-[#062b1f] mb-4">{{ value.title }}</h3>
            <p class="text-gray-600 leading-relaxed">
              {{ value.description }}
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Key Capabilities -->
    <section class="py-20 bg-white">
      <div class="max-w-6xl mx-auto px-4 md:px-6">
        <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] text-center mb-16">Our Capabilities</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="capability in capabilities" :key="capability.label" class="text-center">
            <div class="text-5xl font-bold text-[#062b1f] mb-2">{{ capability.value }}</div>
            <div class="text-gray-600 font-medium">{{ capability.label }}</div>
          </div>
        </div>
      </div>
    </section>

   

    <!-- Methodology -->
    <section class="py-20 bg-white">
      <div class="max-w-6xl mx-auto px-4 md:px-6">
        <div class="text-center mb-16">
          <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] mb-6">Our Methodology</h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            We combine cutting-edge neuroscience, behavioral psychology, and big data analytics to understand and influence population behavior.
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div v-for="method in methodology" :key="method.title" class="flex gap-6">
            <div class="flex-shrink-0">
              <div class="w-12 h-12 bg-[#062b1f]/10 rounded-lg flex items-center justify-center">
                <svg class="w-6 h-6 text-[#062b1f]" fill="none" stroke="currentColor" viewBox="0 0 24 24" v-html="method.icon"></svg>
              </div>
            </div>
            <div>
              <h3 class="text-lg font-bold text-[#062b1f] mb-2">{{ method.title }}</h3>
              <p class="text-gray-600 leading-relaxed">{{ method.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Applications -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-6xl mx-auto px-4 md:px-6">
        <h2 class="text-3xl md:text-4xl font-serif text-[#062b1f] text-center mb-16">Applications</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div v-for="application in applications" :key="application.title" class="bg-white p-8 rounded-lg shadow-md">
            <div class="w-14 h-14 bg-[#062b1f]/10 rounded-lg flex items-center justify-center mb-6">
              <svg class="w-7 h-7 text-[#062b1f]" fill="none" stroke="currentColor" viewBox="0 0 24 24" v-html="application.icon"></svg>
            </div>
            <h3 class="text-xl font-bold text-[#062b1f] mb-4">{{ application.title }}</h3>
            <p class="text-gray-600 leading-relaxed mb-4">{{ application.description }}</p>
            <ul class="space-y-2">
              <li v-for="example in application.examples" :key="example" class="text-sm text-gray-500 flex items-start gap-2">
                <span class="text-[#062b1f] mt-1">•</span>
                <span>{{ example }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
const values = [
  {
    title: 'Precision',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 20l-5.447-2.724A1 1 0 013 16.382V5.618a1 1 0 011.447-.894L9 7m0 13l6-3m-6 3V7m6 10l4.553 2.276A1 1 0 0021 18.382V7.618a1 1 0 00-.553-.894L15 4m0 13V4m0 0L9 7"></path>',
    description: 'We operate with surgical accuracy, targeting specific psychographic profiles with tailored messaging and behavioral interventions.'
  },
  {
    title: 'Insight',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"></path>',
    description: 'We look beyond surface-level data, uncovering the deep cognitive patterns and hidden motivators that drive human decision-making.'
  },
  {
    title: 'Influence',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path>',
    description: 'We don\'t just observe behavior—we provide the tools and strategies to shape outcomes through data-driven behavioral control.'
  }
]

const capabilities = [
  { value: '50M+', label: 'Data Points Analyzed' },
  { value: '23', label: 'Personality Clusters' },
  { value: '100+', label: 'Active Campaigns' },
  { value: '15', label: 'Geographic Regions' }
]

const timeline = [
  {
    year: '2019',
    title: 'Foundation',
    description: 'JubJub Lab was founded by a team of neuroscientists and data scientists with a vision to map human behavior at unprecedented scale.'
  },
  {
    year: '2020',
    title: 'Platform Development',
    description: 'Launched our proprietary behavioral analysis platform, integrating personality cluster theory with real-time data aggregation.'
  },
  {
    year: '2021',
    title: 'First Major Campaigns',
    description: 'Successfully deployed behavioral influence campaigns across multiple regions, demonstrating measurable impact on population decision-making.'
  },
  {
    year: '2022',
    title: 'Neuroscience Integration',
    description: 'Integrated advanced neuroscience research into our models, enabling deeper understanding of cognitive triggers and decision pathways.'
  },
  {
    year: '2023',
    title: 'Global Expansion',
    description: 'Expanded operations to 15 geographic regions, processing over 50 million behavioral data points monthly.'
  },
  {
    year: '2024',
    title: 'AI-Enhanced Profiling',
    description: 'Deployed machine learning models that predict individual behavior with unprecedented accuracy based on psychographic profiles.'
  }
]

const methodology = [
  {
    title: 'Data Aggregation',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0 2.21 3.582 4 8 4s8-1.79 8-4M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4m0 5c0 2.21-3.582 4-8 4s-8-1.79-8-4"></path>',
    description: 'Collect and synthesize behavioral data from multiple sources to create comprehensive population profiles.'
  },
  {
    title: 'Personality Clustering',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"></path>',
    description: 'Segment populations into distinct personality clusters based on cognitive patterns, values, and behavioral tendencies.'
  },
  {
    title: 'Neuroscience Application',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>',
    description: 'Apply neuroscience research to understand how the brain processes information and makes decisions under different conditions.'
  },
  {
    title: 'Behavioral Prediction',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"></path>',
    description: 'Use predictive models to forecast how specific populations will respond to different stimuli and messaging strategies.'
  }
]

const applications = [
  {
    title: 'Marketing & Advertising',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5.882V19.24a1.76 1.76 0 01-3.417.592l-2.147-6.15M18 13a3 3 0 100-6M5.436 13.683A4.001 4.001 0 017 6h1.832c4.1 0 7.625-1.234 9.168-3v14c-1.543-1.766-5.067-3-9.168-3H7a3.988 3.988 0 01-1.564-.317z"></path>',
    description: 'Optimize campaigns by targeting the right personality clusters with precision messaging.',
    examples: [
      'Psychographic audience segmentation',
      'Message optimization by cognitive profile',
      'Regional behavior pattern analysis'
    ]
  },
  {
    title: 'Public Opinion Shaping',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"></path>',
    description: 'Influence public perception and decision-making in specific geographic areas.',
    examples: [
      'Sentiment analysis and tracking',
      'Narrative deployment strategies',
      'Opinion shift measurement'
    ]
  },
  {
    title: 'Behavioral Research',
    icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"></path>',
    description: 'Conduct large-scale studies on human behavior, cognition, and decision-making patterns.',
    examples: [
      'Population behavior mapping',
      'Cognitive pattern identification',
      'Decision pathway analysis'
    ]
  }
]
</script>

