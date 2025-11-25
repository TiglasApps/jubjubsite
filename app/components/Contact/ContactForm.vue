<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
        <!-- Contact Info -->
        <div>
          <h2 class="text-3xl font-serif text-[#062b1f] mb-8">Get in Touch</h2>
          <p class="text-gray-600 text-lg mb-12 leading-relaxed">
            Whether you have a question about our research, partnering opportunities, or careers, we're here to help.
          </p>

          <div class="space-y-8">
            <div class="flex items-start">
              <div class="w-12 h-12 bg-[#062b1f]/5 rounded-full flex items-center justify-center mr-6 flex-shrink-0">
                <span class="text-2xl">📍</span>
              </div>
              <div>
                <h3 class="font-bold text-[#062b1f] mb-1">Headquarters</h3>
                <p class="text-gray-600">
                  Trento<br>
                  Italy
                </p>
              </div>
            </div>

            <div class="flex items-start">
              <div class="w-12 h-12 bg-[#062b1f]/5 rounded-full flex items-center justify-center mr-6 flex-shrink-0">
                <span class="text-2xl">📧</span>
              </div>
              <div>
                <h3 class="font-bold text-[#062b1f] mb-1">Email</h3>
                <p class="text-gray-600">info@jubjublab.com</p>
              </div>
            </div>

            <div class="flex items-start">
              <div class="w-12 h-12 bg-[#062b1f]/5 rounded-full flex items-center justify-center mr-6 flex-shrink-0">
                <span class="text-2xl">📱</span>
              </div>
              <div>
                <h3 class="font-bold text-[#062b1f] mb-1">Media Inquiries</h3>
                <p class="text-gray-600">press@jubjublab.com</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Form -->
        <div class="bg-gray-50 p-8 rounded-2xl">
          <form @submit.prevent="submitForm" class="space-y-6">
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Name *</label>
              <input 
                type="text"
                v-model="formData.name"
                required
                class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all text-gray-900"
                placeholder="Your name"
              >
            </div>
            
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Email *</label>
              <input 
                type="email"
                v-model="formData.email"
                required
                class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all text-gray-900"
                placeholder="your@email.com"
              >
            </div>

            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Subject</label>
              <select v-model="formData.subject" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all bg-white text-gray-900">
                <option>General Inquiry</option>
                <option>Careers</option>
                <option>Partnering</option>
                <option>Media</option>
              </select>
            </div>

            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Message *</label>
              <textarea 
                rows="4"
                v-model="formData.message"
                required
                class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all text-gray-900"
                placeholder="How can we help?"
              ></textarea>
            </div>

            <button 
              type="submit"
              :disabled="!isFormValid"
              :class="[
                'w-full py-4 font-bold rounded-lg transition-all duration-300',
                isFormValid 
                  ? 'bg-[#062b1f] text-white hover:bg-[#1FA34A] cursor-pointer' 
                  : 'bg-gray-300 text-gray-500 cursor-not-allowed'
              ]"
            >
              Send Message
            </button>
          </form>
        </div>
      </div>
    </div>

    <!-- Toast Notification -->
    <Transition name="toast">
      <div v-if="showToast" class="fixed bottom-8 right-8 bg-[#1FA34A] text-white px-6 py-4 rounded-lg shadow-2xl flex items-center gap-3 z-50">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
        </svg>
        <span class="font-semibold">Message sent successfully!</span>
      </div>
    </Transition>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const formData = ref({
  name: '',
  email: '',
  subject: 'General Inquiry',
  message: ''
})

const showToast = ref(false)

const isFormValid = computed(() => {
  return formData.value.name.trim() !== '' && 
         formData.value.email.trim() !== '' && 
         formData.value.message.trim() !== ''
})

const submitForm = () => {
  if (!isFormValid.value) return
  
  // Placeholder for form submission logic
  console.log('Form submitted:', formData.value)
  
  // Show toast notification
  showToast.value = true
  
  // Reset form
  formData.value = {
    name: '',
    email: '',
    subject: 'General Inquiry',
    message: ''
  }
  
  // Hide toast after 3 seconds
  setTimeout(() => {
    showToast.value = false
  }, 3000)
}
</script>

<style scoped>
.toast-enter-active,
.toast-leave-active {
  transition: all 0.3s ease;
}

.toast-enter-from {
  transform: translateX(100%);
  opacity: 0;
}

.toast-leave-to {
  transform: translateY(100%);
  opacity: 0;
}
</style>
