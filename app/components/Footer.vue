<template>
  <footer class="bg-[#041f16] text-white py-12 border-t border-white/10">
    <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-4 gap-8">
      
      <!-- Brand -->
      <div class="col-span-1 md:col-span-1">
        <h2 class="text-2xl font-bold mb-4">JubJub Lab</h2>
        <p class="text-sm text-gray-400 leading-relaxed">
          Mapping the human mind to predict and shape the future.
        </p>
      </div>

      <!-- Links 1 -->
      <div>
        <h3 class="text-sm font-semibold uppercase tracking-wider text-gray-500 mb-4">Company</h3>
        <ul class="space-y-2 text-sm text-gray-300">
          <li><NuxtLink to="/about" class="hover:text-white transition-colors">About Us</NuxtLink></li>
          <li><NuxtLink to="/leadership" class="hover:text-white transition-colors">Leadership</NuxtLink></li>
          <li><NuxtLink to="/careers" class="hover:text-white transition-colors">Careers</NuxtLink></li>
          <li><NuxtLink to="/contact" class="hover:text-white transition-colors">Contact</NuxtLink></li>
        </ul>
      </div>

      <!-- Links 2 -->
      <div>
        <h3 class="text-sm font-semibold uppercase tracking-wider text-gray-500 mb-4">Science</h3>
        <ul class="space-y-2 text-sm text-gray-300">
          <li><NuxtLink to="/research" class="hover:text-white transition-colors">Research</NuxtLink></li>
          <li><NuxtLink to="/publications" class="hover:text-white transition-colors">Publications</NuxtLink></li>
          <li><NuxtLink to="/research" class="hover:text-white transition-colors">Technology</NuxtLink></li>
        </ul>
      </div>


    </div>
    <div class="max-w-7xl mx-auto px-6 mt-12 pt-8 border-t border-white/5 text-center md:text-left text-xs text-gray-500">
      &copy; 2025 JubJub Lab. All rights reserved.
    </div>
  </footer>
</template>
