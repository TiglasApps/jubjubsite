<template>

    <section class="w-full bg-[#f5f3ef] py-20">
      <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-3 gap-8">

        <!-- Card 1 -->
        <NuxtLink to="/research" class="relative group cursor-pointer overflow-hidden rounded-lg shadow-lg hover:shadow-2xl transition-all duration-500 hover:-translate-y-2 block">
          <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=2670&auto=format&fit=crop" class="w-full h-[480px] object-cover transition-transform duration-700 group-hover:scale-110" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/40 to-transparent flex flex-col justify-end p-8 text-white">
            <div class="w-10 h-[2px] bg-white mb-3 transition-all duration-300 group-hover:w-20"></div>
            <h3 class="text-2xl font-serif mb-2">Psychographic Profiling</h3>
            <p class="text-lg opacity-90 transform translate-y-4 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition-all duration-500">Deep analysis of personality traits to predict and influence individual behavior.</p>
          </div>
        </NuxtLink>

        <!-- Card 2 -->
        <NuxtLink to="/research" class="relative group cursor-pointer overflow-hidden rounded-lg shadow-lg hover:shadow-2xl transition-all duration-500 hover:-translate-y-2 block">
          <img src="https://images.unsplash.com/photo-1504868584819-f8e8b4b6d7e3?q=80&w=2676&auto=format&fit=crop" class="w-full h-[480px] object-cover transition-transform duration-700 group-hover:scale-110" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/40 to-transparent flex flex-col justify-end p-8 text-white">
            <div class="w-10 h-[2px] bg-white mb-3 transition-all duration-300 group-hover:w-20"></div>
            <h3 class="text-2xl font-serif mb-2">Predictive Modeling</h3>
            <p class="text-lg opacity-90 transform translate-y-4 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition-all duration-500">Advanced algorithms that forecast population trends and decision-making patterns.</p>
          </div>
        </NuxtLink>

        <!-- Card 3 -->
        <NuxtLink to="/research" class="relative group cursor-pointer overflow-hidden rounded-lg shadow-lg hover:shadow-2xl transition-all duration-500 hover:-translate-y-2 block">
          <img src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=2672&auto=format&fit=crop" class="w-full h-[480px] object-cover transition-transform duration-700 group-hover:scale-110" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/40 to-transparent flex flex-col justify-end p-8 text-white">
            <div class="w-10 h-[2px] bg-white mb-3 transition-all duration-300 group-hover:w-20"></div>
            <h3 class="text-2xl font-serif mb-2">Territorial Mapping</h3>
            <p class="text-lg opacity-90 transform translate-y-4 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition-all duration-500">Geospatial analysis of behavioral data to target specific regions and demographics.</p>
          </div>
        </NuxtLink>

      </div>
    </section>
</template>

<script setup lang="ts">

</script>