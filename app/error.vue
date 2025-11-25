<template>
  <div class="min-h-screen bg-[#062b1f] flex items-center justify-center">
    <!-- Content -->
    <div class="max-w-4xl mx-auto px-6 text-center text-white">
      <!-- Error Code - Large and Clear -->
      <h1 class="text-[8rem] md:text-[12rem] font-bold leading-none mb-8 text-white">
        {{ error.statusCode }}
      </h1>

      <!-- Error Title -->
      <h2 class="text-3xl md:text-5xl font-serif mb-6">
        {{ errorTitle }}
      </h2>

      <!-- Error Message -->
      <p class="text-xl md:text-2xl text-white/70 leading-relaxed max-w-2xl mx-auto mb-12">
        {{ errorMessage }}
      </p>

      <!-- Action Button -->
      <NuxtLink 
        to="/" 
        class="inline-block px-8 py-3 border-2 border-white text-white font-medium text-lg hover:bg-white hover:text-[#062b1f] transition-all"
      >
        Return to Homepage
      </NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  error: {
    type: Object,
    required: true
  }
})

const errorTitle = computed(() => {
  switch (props.error.statusCode) {
    case 404:
      return 'Page Not Found'
    case 403:
      return 'Access Denied'
    case 500:
      return 'Server Error'
    default:
      return 'Error'
  }
})

const errorMessage = computed(() => {
  switch (props.error.statusCode) {
    case 404:
      return 'The page you are looking for does not exist or has been moved.'
    case 403:
      return 'You do not have permission to access this resource.'
    case 500:
      return 'An unexpected error occurred. Please try again later.'
    default:
      return 'Something went wrong. Please try again.'
  }
})
</script>
