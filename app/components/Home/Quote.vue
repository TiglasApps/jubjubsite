<template>
  <section
    class="w-full py-28 flex justify-center bg-[#111] relative overflow-hidden"
  >
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 opacity-20">
        <img :src="backgroundImage" class="w-full h-full object-cover" />
    </div>
    
    <div class="w-[60%] max-w-[900px] relative z-10">
      <p class="text-[34px] leading-snug text-white font-serif mb-10">
        “Data is not just a record of the past; it is the blueprint of the future. By understanding the patterns of human thought, we do not just predict reality—we construct it.”
      </p>

      <div class="mt-5">
        <div class="font-semibold text-[18px] text-gray-300 font-serif">Dr. Aris Thorne</div>
        <div class="text-[16px] text-gray-400 font-serif">Chief Behavioral Scientist</div>
      </div>
    </div>
  </section>
</template>

<script setup>
const backgroundImage = 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=2672&auto=format&fit=crop' 
</script>
