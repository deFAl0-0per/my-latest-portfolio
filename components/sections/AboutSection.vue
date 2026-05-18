<template>
  <section id="about" class="py-24 relative overflow-hidden">
    <div class="absolute right-0 top-1/2 -translate-y-1/2 w-96 h-96 bg-indigo-500/5 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid lg:grid-cols-2 gap-16 items-center">

        <!-- Left - Stats cards -->
        <div class="grid grid-cols-2 gap-4 reveal">
          <div v-for="stat in stats" :key="stat.label"
            class="card group hover:scale-105 transition-transform duration-300"
          >
            <div class="text-3xl font-black gradient-text mb-1">{{ stat.value }}</div>
            <div class="text-gray-400 text-sm">{{ stat.label }}</div>
            <div class="mt-3 h-1 rounded-full bg-dark-600">
              <div class="h-1 rounded-full bg-gradient-to-r from-primary-500 to-teal-400 transition-all duration-1000" :style="`width: ${stat.bar}%`" />
            </div>
          </div>

          <!-- Tech highlight card -->
          <div class="col-span-2 card bg-gradient-to-br from-primary-500/10 to-teal-500/5 border-primary-500/20">
            <div class="flex items-start gap-3">
              <div class="w-10 h-10 rounded-lg bg-primary-500/20 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-primary-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
                </svg>
              </div>
              <div>
                <div class="text-white font-semibold mb-1">Currently Working On</div>
                <div class="text-gray-400 text-sm">Beyond Borders WMS — a full-stack Warehouse Management System with Go Gin + Next.js, serving a Singapore e-commerce client.</div>
              </div>
            </div>
          </div>
        </div>

        <!-- Right - Text content -->
        <div class="space-y-6 reveal">
          <div>
            <p class="section-subtitle">// about me</p>
            <h2 class="section-title">Who I Am</h2>
          </div>

          <div class="space-y-4 text-gray-400 leading-relaxed">
            <p>
              I'm a <span class="text-white font-medium">Full-Stack Developer</span> from Jakarta, Indonesia,
              currently studying Application Network Informatics Systems at
              <span class="text-primary-400">SMKN 69 Jakarta</span>. I am highly enthusiastic about IT
              developments, especially in software engineering.
            </p>
            <p>
              My expertise spans both backend and frontend development — I love building robust
              <span class="text-white font-medium"> RESTful APIs</span> with Go and Laravel, and crafting
              modern, responsive UIs with <span class="text-white font-medium">Nuxt.js / Next.js</span>
              and TailwindCSS.
            </p>
            <p>
              I've delivered production-ready systems for multiple clients including
              <span class="text-primary-400">PT. Solu Filantropi Teknologi</span>,
              <span class="text-primary-400">PT. LSP Gatensi Karya Konstruksi</span>, and
              <span class="text-primary-400">Beyond Borders Singapore</span> — handling everything
              from VPS deployment to database architecture.
            </p>
          </div>

          <!-- Key attributes -->
          <div class="flex flex-col gap-3">
            <div v-for="attr in attributes" :key="attr.text" class="flex items-center gap-3">
              <div class="w-5 h-5 rounded-full bg-primary-500/20 flex items-center justify-center flex-shrink-0">
                <svg class="w-3 h-3 text-primary-400" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/>
                </svg>
              </div>
              <span class="text-gray-300 text-sm">{{ attr.text }}</span>
            </div>
          </div>

          <div class="flex gap-4">
            <a href="mailto:ibra030107@gmail.com" class="btn-primary">
              Contact Me
            </a>
            <a href="tel:+6285692945163" class="btn-outline">
              +62 856 9294 5163
            </a>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const stats = [
  { value: '2+',  label: 'Years Experience', bar: 60 },
  { value: '10+', label: 'Projects Built',    bar: 75 },
  { value: '3',   label: 'Company Clients',   bar: 50 },
  { value: '5+',  label: 'Tech Stacks',       bar: 85 }
]

const attributes = [
  { text: 'Full-Stack Web Development (Laravel, Go, Nuxt, Next)' },
  { text: 'RESTful API design and JWT authentication' },
  { text: 'VPS deployment and server configuration (Biznet Gio)' },
  { text: 'Database management — PostgreSQL, MySQL, MongoDB' },
  { text: 'Real-time features with WebSocket / AJAX Polling' }
]
</script>
