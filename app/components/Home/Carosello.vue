<template>
  <section class="w-full bg-[#062b1f] py-16 md:py-24">
    <div class="max-w-[1400px] mx-auto px-4 md:px-6">
      
      <div class="relative w-full h-[600px] rounded-2xl overflow-hidden shadow-2xl group">
        
        <!-- Slides -->
        <div class="relative w-full h-full">
          <TransitionGroup name="fade">
            <div 
              v-for="(slide, index) in slides" 
              :key="slide.image"
              v-show="current === index"
              class="absolute inset-0 w-full h-full"
            >
              <!-- Image -->
              <img 
                :src="slide.image" 
                class="w-full h-full object-cover transition-transform duration-[10s] ease-linear transform scale-100 group-hover:scale-105"
              />
              
              <!-- Gradient Overlay -->
              <div class="absolute inset-0 bg-gradient-to-r from-[#062b1f]/90 via-[#062b1f]/40 to-transparent"></div>

              <!-- Content -->
              <div class="absolute inset-0 flex flex-col justify-center px-12 md:px-24 max-w-3xl">
                <span class="text-[#1FA34A] font-bold tracking-wider uppercase mb-4 opacity-0 animate-slide-up" style="animation-delay: 0.3s">
                  {{ slide.tag }}
                </span>
                <h2 class="text-4xl md:text-6xl font-serif text-white mb-6 leading-tight opacity-0 animate-slide-up" style="animation-delay: 0.5s">
                  {{ slide.title }}
                </h2>
                <p class="text-lg md:text-xl text-gray-200 mb-8 leading-relaxed opacity-0 animate-slide-up" style="animation-delay: 0.7s">
                  {{ slide.description }}
                </p>
                
                <div class="opacity-0 animate-slide-up" style="animation-delay: 0.9s">
                  <NuxtLink 
                    :to="slide.link"
                    class="inline-flex items-center px-8 py-3 border border-white text-white font-semibold rounded-full hover:bg-white hover:text-[#062b1f] transition-all duration-300"
                  >
                    Learn More
                    <span class="ml-2">→</span>
                  </NuxtLink>
                </div>
              </div>
            </div>
          </TransitionGroup>
        </div>

        <!-- Controls -->
        <div class="absolute bottom-8 right-8 flex items-center space-x-4 z-20">
          <!-- Prev Button -->
          <button 
            @click="prevSlide" 
            class="w-12 h-12 flex items-center justify-center rounded-full border border-white/30 text-white hover:bg-white hover:text-[#062b1f] backdrop-blur-sm transition-all"
          >
            ←
          </button>
          
          <!-- Next Button -->
          <button 
            @click="nextSlide" 
            class="w-12 h-12 flex items-center justify-center rounded-full border border-white/30 text-white hover:bg-white hover:text-[#062b1f] backdrop-blur-sm transition-all"
          >
            →
          </button>
        </div>

        <!-- Indicators -->
        <div class="absolute bottom-8 left-12 flex space-x-3 z-20">
          <button 
            v-for="(_, index) in slides" 
            :key="index"
            @click="current = index"
            :class="[
              'h-1 transition-all duration-300 rounded-full',
              current === index ? 'w-8 bg-white' : 'w-4 bg-white/40 hover:bg-white/60'
            ]"
          ></button>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const current = ref(0)
const autoplayInterval = ref<NodeJS.Timeout | null>(null)

const slides = [
  {
    tag: 'Innovation',
    title: 'Behavioral Prediction',
    description: 'We use advanced computing and massive datasets to forecast individual and collective human actions with unprecedented accuracy.',
    image: 'https://images.unsplash.com/photo-1518186285589-2f7649de83e0?q=80&w=2574&auto=format&fit=crop',
    link: '/research'
  },
  {
    tag: 'Power',
    title: 'Mass Influence',
    description: 'Our strategies shape public opinion and guide societal trends through subtle, data-driven interventions.',
    image: 'https://images.unsplash.com/photo-1556761175-5973dc0f32e7?q=80&w=2670&auto=format&fit=crop',
    link: '/projects-development'
  },
  {
    tag: 'Security',
    title: 'Cognitive Security',
    description: 'Protecting and analyzing the information landscape to ensure stability and predictability in a chaotic world.',
    image: 'https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2670&auto=format&fit=crop',
    link: '/about'
  }
]

const nextSlide = () => {
  current.value = (current.value + 1) % slides.length
  resetAutoplay()
}

const prevSlide = () => {
  current.value = (current.value - 1 + slides.length) % slides.length
  resetAutoplay()
}

const startAutoplay = () => {
  autoplayInterval.value = setInterval(() => {
    current.value = (current.value + 1) % slides.length
  }, 6000)
}

const resetAutoplay = () => {
  if (autoplayInterval.value) clearInterval(autoplayInterval.value)
  startAutoplay()
}

onMounted(() => {
  startAutoplay()
})

onUnmounted(() => {
  if (autoplayInterval.value) clearInterval(autoplayInterval.value)
})
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slide-up {
  animation: slideUp 0.8s ease-out forwards;
}
</style>