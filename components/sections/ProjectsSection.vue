<template>
  <section id="projects" class="py-24 relative overflow-hidden">
    <div class="absolute left-1/2 bottom-0 -translate-x-1/2 w-[800px] h-96 bg-primary-500/5 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16 reveal">
        <p class="section-subtitle">// personal & freelance</p>
        <h2 class="section-title">Projects</h2>
        <p class="text-gray-400 max-w-xl mx-auto mt-3">
          A selection of projects I've built — from personal experiments to client-facing production systems.
        </p>
      </div>

      <!-- Filter -->
      <div class="flex flex-wrap justify-center gap-3 mb-10 reveal">
        <button
          v-for="f in filters"
          :key="f"
          @click="activeFilter = f"
          class="px-4 py-1.5 rounded-full text-sm font-medium transition-all duration-300 border"
          :class="activeFilter === f
            ? 'bg-primary-500 text-dark-900 border-primary-500 shadow-lg shadow-primary-500/30'
            : 'border-dark-600 text-gray-400 hover:text-primary-400 hover:border-primary-500/40'"
        >
          {{ f }}
        </button>
      </div>

      <!-- Projects grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6 reveal">
        <TransitionGroup name="project-card">
          <div
            v-for="project in filteredProjects"
            :key="project.title"
            class="card group flex flex-col hover:border-primary-500/40 hover:-translate-y-2 transition-all duration-300"
          >
            <!-- Header -->
            <div class="flex items-start justify-between mb-4">
              <div class="w-12 h-12 rounded-xl flex items-center justify-center text-2xl" :class="project.iconBg">
                {{ project.icon }}
              </div>
              <div class="flex items-center gap-2">
                <a
                  v-if="project.link"
                  :href="project.link"
                  target="_blank"
                  class="w-8 h-8 flex items-center justify-center rounded-lg border border-dark-600 text-gray-500 hover:text-primary-400 hover:border-primary-500/50 transition-all"
                >
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/>
                  </svg>
                </a>
              </div>
            </div>

            <!-- Content -->
            <div class="flex-1">
              <div class="flex items-center gap-2 mb-1">
                <h3 class="text-white font-bold text-lg">{{ project.title }}</h3>
              </div>
              <div class="flex items-center gap-2 mb-3">
                <span class="text-xs text-gray-500 font-mono">{{ project.period }}</span>
                <span class="text-xs px-2 py-0.5 rounded-full font-mono"
                  :class="project.type === 'Freelance' ? 'bg-green-500/10 text-green-400' : project.type === 'Company' ? 'bg-blue-500/10 text-blue-400' : 'bg-gray-500/10 text-gray-400'"
                >
                  {{ project.type }}
                </span>
              </div>
              <p class="text-gray-400 text-sm leading-relaxed mb-4">{{ project.description }}</p>
            </div>

            <!-- Tags -->
            <div class="flex flex-wrap gap-1.5">
              <span v-for="tech in project.tech" :key="tech" class="tag text-xs">{{ tech }}</span>
            </div>
          </div>
        </TransitionGroup>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const activeFilter = ref('All')

const filters = ['All', 'Freelance', 'Company', 'Personal']

const projects = [
  {
    title: 'Beyond Borders WMS',
    icon: '🏭',
    iconBg: 'bg-blue-500/10',
    period: 'March 2026 — Now',
    type: 'Freelance',
    filter: 'Freelance',
    link: 'https://wms.beyondborders.sg',
    description: 'Full-stack Warehouse Management System for a Singapore e-commerce client. Integrates Shopee, Lazada, Shopify, EasyParcel, and HitPay in one dashboard.',
    tech: ['Go Gin', 'Next.js', 'PostgreSQL', 'MinIO', 'WebSocket']
  },
  {
    title: 'Beyond Borders Landing',
    icon: '🌏',
    iconBg: 'bg-teal-500/10',
    period: 'March 2026 — Now',
    type: 'Freelance',
    filter: 'Freelance',
    link: 'https://beyondborders.sg',
    description: 'Conversion-focused landing page for a Singapore fulfillment platform. Built with Nuxt.js SSR for optimal SEO and performance.',
    tech: ['Nuxt.js', 'Vue 3', 'TailwindCSS', 'SSR']
  },
  {
    title: 'Taskia Digital Web',
    icon: '🏫',
    iconBg: 'bg-indigo-500/10',
    period: 'Jan 2026 — Feb 2026',
    type: 'Company',
    filter: 'Company',
    link: 'https://tasdig.solu.co.id/login',
    description: 'School management web app — attendance, grades, extracurricular, and permits. Features real-time AJAX notifications.',
    tech: ['Laravel 10', 'Bootstrap 4', 'AJAX', 'MySQL']
  },
  {
    title: 'My Gatensi Web',
    icon: '📋',
    iconBg: 'bg-orange-500/10',
    period: 'Dec 2025 — Feb 2026',
    type: 'Company',
    filter: 'Company',
    link: 'https://reguler.lspgatensi.id/login',
    description: 'Certification assessment management system with automated certificate generation, payment confirmation, and VPS deployment.',
    tech: ['Laravel 10', 'TailwindCSS', 'MySQL', 'VPS']
  },
  {
    title: 'Easy Laundry Web',
    icon: '👕',
    iconBg: 'bg-cyan-500/10',
    period: 'Dec 2025 — Feb 2026',
    type: 'Personal',
    filter: 'Personal',
    link: null,
    description: 'Real-time laundry monitoring platform with live dashboards, washing history, user management, and daily revenue calculation.',
    tech: ['Laravel 8', 'Blade', 'Vanilla CSS', 'MySQL']
  },
  {
    title: 'Rabook Store Web',
    icon: '📚',
    iconBg: 'bg-purple-500/10',
    period: 'Dec 2025 — Feb 2026',
    type: 'Personal',
    filter: 'Personal',
    link: null,
    description: 'Digital book marketplace with role-based access (Admin/User), product management, and activity logging for full transparency.',
    tech: ['Laravel 10', 'TailwindCSS', 'MySQL', 'RBAC']
  },
  {
    title: 'EV Bus SureDrive Web',
    icon: '🚌',
    iconBg: 'bg-green-500/10',
    period: 'Aug 2025 — Oct 2025',
    type: 'Company',
    filter: 'Company',
    link: 'https://api.suredrive-adas.smartpamobvit.id/',
    description: 'IoT dashboard for monitoring electric vehicles with Teltonika ADAS cameras, tracking driver behavior and vehicle events in real time.',
    tech: ['Laravel 8', 'TailwindCSS', 'IoT', 'Real-time']
  },
  {
    title: 'Alarm System RESTful API',
    icon: '🔔',
    iconBg: 'bg-red-500/10',
    period: 'Jun 2025 — Jul 2025',
    type: 'Company',
    filter: 'Company',
    link: null,
    description: 'Structured RESTful API for alarm management built with Go Fiber. Implements JWT auth, GORM, and PostgreSQL for a scalable backend.',
    tech: ['Go Fiber', 'JWT', 'GORM', 'PostgreSQL']
  }
]

const filteredProjects = computed(() =>
  activeFilter.value === 'All'
    ? projects
    : projects.filter(p => p.filter === activeFilter.value)
)
</script>

<style scoped>
.project-card-enter-active,
.project-card-leave-active {
  transition: all 0.3s ease;
}
.project-card-enter-from,
.project-card-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>
