<template>
  <section id="education" class="py-24 relative overflow-hidden">
    <div class="absolute right-0 bottom-0 w-80 h-80 bg-indigo-500/5 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16 reveal">
        <p class="section-subtitle">// education & internship</p>
        <h2 class="section-title">Education</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-8">
        <!-- Education Card -->
        <div class="card hover:border-primary-500/40 transition-all duration-300 reveal">
          <div class="flex items-start gap-4">
            <div class="w-14 h-14 rounded-2xl bg-primary-500/10 flex items-center justify-center text-3xl flex-shrink-0">
              🎓
            </div>
            <div>
              <span class="tag mb-2 inline-block">Formal Education</span>
              <h3 class="text-white font-bold text-xl">Application Network Informatics System</h3>
              <p class="text-primary-400 font-medium mt-1">SMKN 69 Jakarta</p>
              <div class="flex items-center gap-2 mt-2">
                <svg class="w-4 h-4 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/>
                </svg>
                <span class="text-gray-400 text-sm font-mono">May 2022 — May 2026</span>
              </div>
              <div class="flex items-center gap-2 mt-1">
                <svg class="w-4 h-4 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                </svg>
                <span class="text-gray-400 text-sm">Jakarta Timur</span>
              </div>
              <p class="text-gray-400 text-sm leading-relaxed mt-4">
                4-year IT Vocational School program focused on software engineering, networking, and information systems.
                Highly enthusiastic about IT developments, especially in the field of web and application development.
              </p>
            </div>
          </div>
        </div>

        <!-- Internships -->
        <div class="space-y-4 reveal">
          <div v-for="intern in internships" :key="intern.company"
            class="card hover:border-primary-500/40 transition-all duration-300"
          >
            <div class="flex items-start gap-4">
              <div class="w-10 h-10 rounded-xl flex items-center justify-center text-xl flex-shrink-0" :class="intern.iconBg">
                {{ intern.icon }}
              </div>
              <div class="flex-1">
                <div class="flex items-start justify-between flex-wrap gap-1">
                  <div>
                    <span class="tag text-xs mb-1 inline-block">Internship</span>
                    <h4 class="text-white font-semibold">{{ intern.role }}</h4>
                    <p class="text-primary-400 text-sm">{{ intern.company }}</p>
                  </div>
                  <div class="text-right">
                    <div class="text-gray-400 text-xs font-mono">{{ intern.period }}</div>
                    <div class="text-gray-500 text-xs">{{ intern.location }}</div>
                  </div>
                </div>
                <p class="text-gray-400 text-sm mt-2 leading-relaxed">{{ intern.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const internships = [
  {
    role: 'Back End Developer',
    company: 'PT. Solu Filantropi Teknologi',
    icon: '⚙️',
    iconBg: 'bg-blue-500/10',
    period: 'Jun 2025 — Apr 2026',
    location: 'Jakarta Selatan',
    description: 'Developed and maintained multiple web applications by building RESTful APIs, managing databases, and implementing business logic. Collaborated with frontend developers for seamless system integration.'
  },
  {
    role: 'Full-Stack Developer',
    company: 'PT. LSP Gatensi Karya Konstruksi',
    icon: '🏗️',
    iconBg: 'bg-orange-500/10',
    period: 'Jun 2025 — Apr 2026',
    location: 'Jakarta Selatan',
    description: 'Handled core certification features including participant data retrieval, payment confirmation, identity verification, assessment scheduling, and automated certificate generation.'
  }
]
</script>
