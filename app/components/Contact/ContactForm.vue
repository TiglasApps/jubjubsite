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
                  1170 Veterans Blvd<br>
                  South San Francisco, CA 94080
                </p>
              </div>
            </div>

            <div class="flex items-start">
              <div class="w-12 h-12 bg-[#062b1f]/5 rounded-full flex items-center justify-center mr-6 flex-shrink-0">
                <span class="text-2xl">📧</span>
              </div>
              <div>
                <h3 class="font-bold text-[#062b1f] mb-1">Email</h3>
                <p class="text-gray-600">info@calicolabs.com</p>
              </div>
            </div>

            <div class="flex items-start">
              <div class="w-12 h-12 bg-[#062b1f]/5 rounded-full flex items-center justify-center mr-6 flex-shrink-0">
                <span class="text-2xl">📱</span>
              </div>
              <div>
                <h3 class="font-bold text-[#062b1f] mb-1">Media Inquiries</h3>
                <p class="text-gray-600">press@calicolabs.com</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Form -->
        <div class="bg-gray-50 p-8 rounded-2xl">
          <form @submit.prevent="submitForm" class="space-y-6">
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Name</label>
              <input 
                type="text" 
                class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all"
                placeholder="Your name"
              >
            </div>
            
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Email</label>
              <input 
                type="email" 
                class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all"
                placeholder="your@email.com"
              >
            </div>

            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Subject</label>
              <select class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all bg-white">
                <option>General Inquiry</option>
                <option>Careers</option>
                <option>Partnering</option>
                <option>Media</option>
              </select>
            </div>

            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2">Message</label>
              <textarea 
                rows="4"
                class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-[#1FA34A] focus:ring-2 focus:ring-[#1FA34A]/20 outline-none transition-all"
                placeholder="How can we help?"
              ></textarea>
            </div>

            <button 
              type="submit"
              class="w-full py-4 bg-[#062b1f] text-white font-bold rounded-lg hover:bg-[#1FA34A] transition-colors duration-300"
            >
              Send Message
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const submitForm = () => {
  // Placeholder for form submission logic
  console.log('Form submitted')
}
</script>
