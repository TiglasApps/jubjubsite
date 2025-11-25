<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-4 md:px-6">
      <div class="mb-12">
        <h2 class="text-3xl font-serif text-[#062b1f] mb-4">Open Positions</h2>
        <p class="text-gray-600 max-w-xl">
          We're looking for people who share our vision and passion for understanding and shaping the human mind. Join us in exploring the frontiers of behavioral science and human cognition.
        </p>
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
            
            <button 
              @click="openModal(job)"
              class="px-6 py-2 bg-[#062b1f] text-white rounded-full opacity-0 group-hover:opacity-100 transform translate-x-4 group-hover:translate-x-0 transition-all duration-300"
            >
              Apply Now
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Application Modal -->
    <Transition name="modal">
      <div v-if="selectedJob" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/60" @click.self="closeModal">
        <div class="bg-white rounded-xl max-w-3xl w-full max-h-[90vh] overflow-y-auto shadow-2xl">
          <!-- Header -->
          <div class="sticky top-0 bg-[#062b1f] text-white p-6 rounded-t-xl">
            <div class="flex justify-between items-start">
              <div>
                <span class="inline-block px-3 py-1 bg-white/20 text-white text-xs font-semibold tracking-wider uppercase rounded-full mb-3">
                  {{ selectedJob.department }}
                </span>
                <h2 class="text-2xl md:text-3xl font-serif">{{ selectedJob.title }}</h2>
                <p class="text-white/80 mt-2">📍 {{ selectedJob.location }} • 🕒 {{ selectedJob.type }}</p>
              </div>
              <button @click="closeModal" class="text-white/80 hover:text-white text-3xl leading-none">&times;</button>
            </div>
          </div>

          <!-- Content -->
          <div class="p-6 md:p-8">
            <!-- Job Description -->
            <div class="mb-8">
              <h3 class="text-xl font-bold text-[#062b1f] mb-4">Position Overview</h3>
              <p class="text-gray-700 leading-relaxed">{{ selectedJob.description }}</p>
            </div>

            <!-- Requirements -->
            <div class="mb-8">
              <h3 class="text-xl font-bold text-[#062b1f] mb-4">Requirements</h3>
              <ul class="space-y-3">
                <li v-for="req in selectedJob.requirements" :key="req" class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-[#1FA34A] flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                  </svg>
                  <span class="text-gray-700">{{ req }}</span>
                </li>
              </ul>
            </div>

            <!-- Benefits & Compensation -->
            <div class="mb-8">
              <h3 class="text-xl font-bold text-[#062b1f] mb-4">Benefits & Compensation</h3>
              <div class="bg-[#1FA34A]/5 border border-[#1FA34A]/20 rounded-lg p-4 mb-4">
                <div class="flex items-center gap-2 mb-2">
                  <svg class="w-5 h-5 text-[#1FA34A]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                  </svg>
                  <span class="font-bold text-[#062b1f]">{{ selectedJob.salary }}</span>
                </div>
              </div>
              <ul class="space-y-3">
                <li v-for="benefit in selectedJob.benefits" :key="benefit" class="flex items-start gap-3">
                  <svg class="w-5 h-5 text-[#1FA34A] flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                  </svg>
                  <span class="text-gray-700">{{ benefit }}</span>
                </li>
              </ul>
            </div>

            <!-- Application Form -->
            <div class="border-t pt-8">
              <h3 class="text-xl font-bold text-[#062b1f] mb-6">Submit Your Application</h3>
              
              <form @submit.prevent="submitApplication" class="space-y-6">
                <!-- Name & Email -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                  <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Full Name *</label>
                  <input 
                    type="text" 
                    required
                    v-model="formData.name"
                    class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#1FA34A] focus:border-transparent outline-none text-gray-900"
                    placeholder="John Doe"
                  />
                  </div>
                  <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Email *</label>
                  <input 
                    type="email" 
                    required
                    v-model="formData.email"
                    class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#1FA34A] focus:border-transparent outline-none text-gray-900"
                    placeholder="john@example.com"
                  />
                  </div>
                </div>

                <!-- LinkedIn -->
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">LinkedIn Profile (Optional)</label>
                  <input 
                    type="url"
                    v-model="formData.linkedin"
                    class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#1FA34A] focus:border-transparent outline-none text-gray-900"
                    placeholder="https://linkedin.com/in/yourprofile"
                  />
                </div>

                <!-- CV Upload - Drag & Drop -->
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Resume/CV *</label>
                  <div 
                    @dragover.prevent="isDragging = true"
                    @dragleave.prevent="isDragging = false"
                    @drop.prevent="handleDrop"
                    :class="[
                      'border-2 border-dashed rounded-lg p-8 text-center transition-all cursor-pointer',
                      isDragging ? 'border-[#1FA34A] bg-[#1FA34A]/5' : 'border-gray-300 hover:border-[#1FA34A]'
                    ]"
                    @click="$refs.fileInput.click()"
                  >
                    <input 
                      ref="fileInput"
                      type="file" 
                      accept=".pdf,.doc,.docx"
                      @change="handleFileSelect"
                      class="hidden"
                    />
                    <div v-if="!uploadedFile">
                      <svg class="w-12 h-12 text-gray-400 mx-auto mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M15 13l-3-3m0 0l-3 3m3-3v12"></path>
                      </svg>
                      <p class="text-gray-600 mb-2">Drag and drop your CV here, or click to browse</p>
                      <p class="text-sm text-gray-500">PDF, DOC, DOCX (Max 10MB)</p>
                    </div>
                    <div v-else class="flex items-center justify-center gap-3">
                      <svg class="w-8 h-8 text-[#1FA34A]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                      </svg>
                      <span class="text-gray-700 font-medium">{{ uploadedFile.name }}</span>
                      <button type="button" @click.stop="removeFile" class="text-red-500 hover:text-red-700">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                        </svg>
                      </button>
                    </div>
                  </div>
                </div>

                <!-- Cover Letter -->
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Cover Letter (Optional)</label>
                  <textarea 
                    v-model="formData.coverLetter"
                    rows="4"
                    class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#1FA34A] focus:border-transparent outline-none resize-none text-gray-900"
                    placeholder="Tell us why you're the perfect fit for this role..."
                  ></textarea>
                </div>

                <!-- Submit Button -->
                <div class="flex gap-4">
                  <button 
                    type="submit"
                    :disabled="!isFormValid"
                    :class="[
                      'flex-1 px-6 py-3 font-semibold rounded-lg transition-all',
                      isFormValid 
                        ? 'bg-[#062b1f] text-white hover:bg-[#0a4d35] cursor-pointer' 
                        : 'bg-gray-300 text-gray-500 cursor-not-allowed'
                    ]"
                  >
                    Submit Application
                  </button>
                  <button 
                    type="button"
                    @click="closeModal"
                    class="px-6 py-3 border-2 border-gray-300 text-gray-700 font-semibold rounded-lg hover:border-gray-400 transition-colors"
                  >
                    Cancel
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </Transition>

    <!-- Toast Notification -->
    <Transition name="toast">
      <div v-if="showToast" class="fixed bottom-8 right-8 bg-[#1FA34A] text-white px-6 py-4 rounded-lg shadow-2xl flex items-center gap-3 z-50">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
        </svg>
        <span class="font-semibold">Application submitted successfully!</span>
      </div>
    </Transition>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const selectedJob = ref(null)
const isDragging = ref(false)
const uploadedFile = ref(null)
const showToast = ref(false)
const formData = ref({
  name: '',
  email: '',
  linkedin: '',
  coverLetter: ''
})

const isFormValid = computed(() => {
  return formData.value.name.trim() !== '' && 
         formData.value.email.trim() !== '' && 
         uploadedFile.value !== null
})

const jobs = [
  {
    id: 1,
    title: 'Senior AI/ML Architect',
    department: 'Artificial Intelligence',
    location: 'Remote',
    type: 'Full-time',
    description: 'Lead the design and implementation of cutting-edge AI/ML systems for behavioral prediction and psychographic profiling. You will architect scalable machine learning pipelines that process millions of data points daily, developing novel algorithms for personality cluster identification and behavioral forecasting.',
    requirements: [
      'PhD in Computer Science, Machine Learning, or Cognitive Science from a top-10 global institution',
      'Multiple first-author publications in NeurIPS, ICML, ICLR, or CVPR with significant citation impact',
      'Demonstrated expertise in novel neural architecture design and algorithmic innovation',
      'Proven ability to architect and deploy ML systems processing petabyte-scale datasets',
      'Deep theoretical understanding of information theory, Bayesian inference, and causal modeling',
      'Track record of patents or breakthrough contributions to open-source ML frameworks',
      'Fluency in multiple programming paradigms and ability to optimize at the hardware level'
    ],
    benefits: [
      'Competitive compensation: $300,000 - $500,000 base + equity',
      'Unlimited PTO with mandatory 4-week minimum',
      'Annual research budget of $50,000 for conferences, equipment, and publications',
      'Access to state-of-the-art GPU clusters and cloud computing resources',
      'Relocation assistance and global remote work flexibility',
      'Comprehensive health, dental, vision, and mental health coverage'
    ],
    salary: '$300K - $500K + Equity'
  },
  {
    id: 2,
    title: 'Lead Full-Stack Developer',
    department: 'Engineering',
    location: 'Remote',
    type: 'Full-time',
    description: 'Architect and develop the core infrastructure powering our behavioral analytics platform. You will lead the development of Node, JubJub, and Guignol systems, building scalable web applications and APIs that handle real-time data processing and visualization for millions of users.',
    requirements: [
      'Mastery of multiple programming languages including TypeScript, Python, Rust, and Go',
      'Architect-level understanding of distributed systems, consensus algorithms, and fault tolerance',
      'Proven ability to design systems handling millions of concurrent users with sub-100ms latency',
      'Deep expertise in database internals, query optimization, and custom storage engine design',
      'Contributions to major open-source projects or creation of widely-adopted libraries/frameworks',
      'Understanding of cryptography, security protocols, and zero-trust architecture',
      'Ability to mentor and elevate engineering teams while maintaining hands-on technical excellence'
    ],
    benefits: [
      'Competitive compensation: $250,000 - $400,000 base + equity',
      'Flexible work schedule with async-first culture',
      'Top-tier hardware and software tools of your choice',
      'Annual professional development budget of $25,000',
      'Stock options with accelerated vesting schedule',
      'Premium health insurance with family coverage'
    ],
    salary: '$250K - $400K + Equity'
  },
  {
    id: 3,
    title: 'Chief Commercial Officer',
    department: 'Commercial Strategy',
    location: 'Remote',
    type: 'Executive',
    description: 'Drive global commercial strategy and revenue growth for our behavioral analytics and influence platforms. You will establish partnerships with Fortune 500 companies, government agencies, and international organizations, positioning our technology as the industry standard for data-driven decision making.',
    requirements: [
      'Demonstrated success generating $100M+ in annual revenue for technology or data companies',
      'Extensive C-suite network across Fortune 500, government, and international organizations',
      'Proven ability to negotiate and close 8-figure contracts with sovereign entities',
      'Deep understanding of geopolitical dynamics, regulatory frameworks, and ethical AI governance',
      'MBA or equivalent from Harvard, Stanford, Wharton, INSEAD, or comparable institution',
      'Fluency in business strategy, behavioral economics, and complex stakeholder management',
      'Track record of building and scaling global commercial organizations from ground up'
    ],
    benefits: [
      'Executive compensation: $400,000 - $700,000 base + significant equity stake',
      'Performance bonuses tied to revenue milestones (up to 200% of base)',
      'Unlimited travel budget for client meetings and strategic partnerships',
      'Executive assistant and dedicated operations support',
      'Board-level strategic input and equity participation',
      'Comprehensive executive benefits package including concierge services'
    ],
    salary: '$400K - $700K + Equity + Bonuses'
  },
  {
    id: 4,
    title: 'International Liaison Officer',
    department: 'Supranational Relations',
    location: 'Remote',
    type: 'Full-time',
    description: 'Serve as the primary interface between JubJub Lab and supranational organizations including the UN, EU, WHO, and other international bodies. You will navigate complex regulatory environments, build strategic relationships with policymakers, and ensure our operations align with international standards while advancing our mission.',
    requirements: [
      'Direct relationships with decision-makers in UN agencies, EU institutions, or equivalent bodies',
      'Advanced degree (JD, PhD, or equivalent) from Oxford, Cambridge, Sciences Po, or top-tier institution',
      'Native-level fluency in English plus three additional UN official languages',
      'Deep expertise in international law, data governance, and cross-border regulatory frameworks',
      'Proven ability to navigate complex bureaucracies and influence policy at the highest levels',
      'Security clearance or ability to obtain one from major Western government',
      'Understanding of intelligence community protocols and classified information handling'
    ],
    benefits: [
      'Competitive compensation: $200,000 - $350,000 base + equity',
      'Diplomatic travel privileges and VIP airport services',
      'Annual budget for international conferences and relationship building',
      'Language training and cultural immersion programs',
      'Flexible schedule accommodating multiple time zones',
      'Premium global health insurance with emergency evacuation coverage'
    ],
    salary: '$200K - $350K + Equity'
  },
  {
    id: 5,
    title: 'Director of Behavioral Analytics',
    department: 'Data Science',
    location: 'Remote',
    type: 'Full-time',
    description: 'Lead our behavioral analytics division, developing advanced models for psychographic profiling, personality clustering, and predictive behavioral analysis. You will oversee a team of data scientists and researchers, driving innovation in how we understand and predict human behavior at scale.',
    requirements: [
      'PhD in Psychology, Neuroscience, Behavioral Economics, or Cognitive Science from elite institution',
      'Groundbreaking published research in behavioral modeling with 1000+ citations',
      'Expertise in psychometric theory, Big Five personality models, and cognitive biases',
      'Mastery of advanced statistical methods, causal inference, and experimental design',
      'Proven ability to translate complex psychological research into scalable technical systems',
      'Deep understanding of ethical considerations in behavioral manipulation and influence',
      'Recognition in academic community through awards, keynotes, or editorial board positions'
    ],
    benefits: [
      'Competitive compensation: $250,000 - $400,000 base + equity',
      'Dual-track career allowing continued academic research and publication',
      'Annual research budget and access to proprietary behavioral datasets',
      'Collaboration opportunities with leading universities and research institutions',
      'Sabbatical options for extended research projects',
      'Comprehensive benefits with mental health and wellness focus'
    ],
    salary: '$250K - $400K + Equity'
  },
  {
    id: 6,
    title: 'Junior Developer',
    department: 'Engineering',
    location: 'Remote',
    type: 'Full-time',
    description: 'Join our engineering team as a Junior Developer and contribute to building innovative web applications and data visualization tools. You will work alongside experienced developers, learning best practices while contributing to real-world projects that impact millions of users. This is an excellent opportunity for recent graduates or career changers to grow their skills in a cutting-edge tech environment.',
    requirements: [
      'Bachelor\'s degree in Computer Science, Engineering, or related field (or equivalent practical experience)',
      'Solid understanding of JavaScript/TypeScript and at least one modern framework (React, Vue, or Angular)',
      'Basic knowledge of HTML, CSS, and responsive web design principles',
      'Familiarity with Git version control and collaborative development workflows',
      'Understanding of RESTful APIs and basic database concepts',
      'Strong problem-solving skills and eagerness to learn new technologies',
      'Good communication skills and ability to work in a team environment'
    ],
    benefits: [
      'Competitive entry-level compensation: $60,000 - $85,000 base + equity',
      'Comprehensive mentorship program with senior developers',
      'Annual learning budget of $3,000 for courses, books, and conferences',
      'Flexible work schedule with remote-first culture',
      'Health, dental, and vision insurance',
      'Career growth opportunities with clear advancement paths',
      'Modern development tools and equipment provided'
    ],
    salary: '$60K - $85K + Equity'
  },
  {
    id: 7,
    title: 'Communications Manager - Entry Level',
    department: 'Marketing & Communications',
    location: 'Remote',
    type: 'Full-time',
    description: 'Launch your career in strategic communications with JubJub Lab. You will help craft compelling narratives about our work, manage social media presence, create content for various platforms, and support our public relations efforts. This role offers hands-on experience in tech communications and the opportunity to shape how we present groundbreaking behavioral science to the world.',
    requirements: [
      'Bachelor\'s degree in Communications, Marketing, Journalism, or related field',
      'Excellent written and verbal communication skills in English (additional languages a plus)',
      'Experience with social media platforms and content management systems',
      'Basic understanding of digital marketing and SEO principles',
      'Strong organizational skills and ability to manage multiple projects',
      'Creative mindset with attention to detail',
      'Portfolio of writing samples or previous content work (academic or professional)'
    ],
    benefits: [
      'Competitive entry-level compensation: $50,000 - $70,000 base + equity',
      'Professional development in strategic communications and PR',
      'Annual budget of $2,000 for professional development and certifications',
      'Flexible remote work with occasional travel opportunities',
      'Health and wellness benefits package',
      'Collaborative team environment with growth opportunities',
      'Access to industry events and networking opportunities'
    ],
    salary: '$50K - $70K + Equity'
  }
]

const openModal = (job) => {
  selectedJob.value = job
  document.body.style.overflow = 'hidden'
}

const closeModal = () => {
  selectedJob.value = null
  uploadedFile.value = null
  formData.value = { name: '', email: '', linkedin: '', coverLetter: '' }
  isDragging.value = false
  document.body.style.overflow = 'auto'
}

const handleDrop = (e) => {
  isDragging.value = false
  const files = e.dataTransfer.files
  if (files.length > 0) {
    uploadedFile.value = files[0]
  }
}

const handleFileSelect = (e) => {
  const files = e.target.files
  if (files.length > 0) {
    uploadedFile.value = files[0]
  }
}

const removeFile = () => {
  uploadedFile.value = null
}

const submitApplication = () => {
  if (!isFormValid.value) return
  
  // Here you would typically send the data to your backend
  console.log('Application submitted:', {
    job: selectedJob.value.title,
    ...formData.value,
    cv: uploadedFile.value.name
  })
  
  // Show toast notification
  showToast.value = true
  
  // Close modal after a short delay
  setTimeout(() => {
    closeModal()
  }, 500)
  
  // Hide toast after 3 seconds
  setTimeout(() => {
    showToast.value = false
  }, 3500)
}
</script>

<style scoped>
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.3s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}

.modal-enter-active .bg-white,
.modal-leave-active .bg-white {
  transition: transform 0.3s ease;
}

.modal-enter-from .bg-white,
.modal-leave-to .bg-white {
  transform: scale(0.9);
}

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
