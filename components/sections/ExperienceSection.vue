<template>
  <section id="experience" class="py-24 relative overflow-hidden">
    <div class="absolute right-0 top-0 w-96 h-96 bg-teal-500/5 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16 reveal">
        <p class="section-subtitle">// work history</p>
        <h2 class="section-title">Work Experience</h2>
        <p class="text-gray-400 max-w-xl mx-auto mt-3">
          Professional experience building real-world systems for companies and clients.
        </p>
      </div>

      <!-- Timeline -->
      <div class="relative">
        <!-- Vertical line -->
        <div class="absolute left-4 md:left-1/2 top-0 bottom-0 w-px bg-gradient-to-b from-primary-500/60 via-primary-500/20 to-transparent" />

        <div class="space-y-12">
          <div
            v-for="(exp, i) in experiences"
            :key="exp.title"
            class="relative flex flex-col md:flex-row gap-8 reveal"
            :class="i % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse'"
          >
            <!-- Timeline dot -->
            <div class="absolute left-4 md:left-1/2 -translate-x-1/2 w-4 h-4 rounded-full bg-primary-500 border-4 border-dark-900 z-10 mt-6" />

            <!-- Spacer -->
            <div class="hidden md:block md:w-1/2" />

            <!-- Card -->
            <div class="ml-12 md:ml-0 md:w-1/2" :class="i % 2 === 0 ? 'md:pl-8' : 'md:pr-8'">
              <div class="card hover:border-primary-500/40 hover:scale-[1.02] transition-all duration-300">
                <div class="flex items-start justify-between mb-3 flex-wrap gap-2">
                  <div>
                    <span class="tag mb-2 inline-block">{{ exp.type }}</span>
                    <h3 class="text-white font-bold text-lg leading-tight">{{ exp.title }}</h3>
                    <p class="text-primary-400 font-medium text-sm mt-0.5">{{ exp.company }}</p>
                  </div>
                  <div class="text-right">
                    <div class="text-gray-400 text-xs font-mono">{{ exp.period }}</div>
                    <div class="text-gray-500 text-xs">{{ exp.location }}</div>
                  </div>
                </div>

                <ul class="space-y-2 mb-4">
                  <li v-for="point in exp.points" :key="point" class="flex items-start gap-2 text-gray-400 text-sm">
                    <span class="text-primary-500 mt-1 flex-shrink-0">▹</span>
                    {{ point }}
                  </li>
                </ul>

                <div class="flex flex-wrap gap-1.5">
                  <span v-for="tech in exp.tech" :key="tech" class="tag text-xs">{{ tech }}</span>
                </div>

                <a
                  v-if="exp.link"
                  :href="exp.link"
                  target="_blank"
                  class="inline-flex items-center gap-1.5 mt-3 text-xs text-primary-400 hover:text-primary-300 transition-colors font-mono"
                >
                  <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/>
                  </svg>
                  {{ exp.link.replace('https://', '') }}
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const experiences = [
  {
    title: 'Beyond Borders WMS Dashboard',
    company: 'Freelance Remote',
    type: 'Full-Stack Web',
    period: 'March 2026 — Now',
    location: 'Remote',
    link: 'https://wms.beyondborders.sg',
    points: [
      'Developed a comprehensive Warehouse Management System with Go Gin backend and Next.js frontend.',
      'Integrated Shopee, Lazada, and Shopify for centralized order synchronization and inventory management.',
      'Implemented EasyParcel for shipping automation and HitPay as payment gateway.',
      'Engineered real-time data layer using WebSocket/SSE, PostgreSQL, and MinIO object storage.'
    ],
    tech: ['Go Gin', 'Next.js', 'PostgreSQL', 'MinIO', 'WebSocket', 'Shopee API', 'HitPay']
  },
  {
    title: 'Beyond Borders WMS Landing Page',
    company: 'Freelance Remote',
    type: 'Front-End Web',
    period: 'March 2026 — Now',
    location: 'Remote',
    link: 'https://beyondborders.sg',
    points: [
      'Built a real-time, responsive landing page using Nuxt.js (Vue) and TailwindCSS.',
      'Leveraged Nuxt.js SSR for optimized SEO performance and fast load speeds.',
      'Designed reusable Vue components for pricing, features, and service flow sections.'
    ],
    tech: ['Nuxt.js', 'Vue 3', 'TailwindCSS', 'SSR', 'SEO']
  },
  {
    title: 'Taskia Digital Web',
    company: 'PT. Solu Filantropi Teknologi',
    type: 'Full-Stack Web',
    period: 'Jan 2026 — Feb 2026',
    location: 'Jakarta Selatan',
    link: 'https://tasdig.solu.co.id/login',
    points: [
      'Designed a web app for school staff and students using Laravel 10 and Bootstrap 4.',
      'Features: student attendance monitoring, grade management, extracurricular activities.',
      'Built real-time sidebar notifications with AJAX Polling and supervisor scheduler.'
    ],
    tech: ['Laravel 10', 'Bootstrap 4', 'AJAX Polling', 'MySQL', 'Supervisor']
  },
  {
    title: 'My Gatensi Web',
    company: 'PT. LSP Gatensi Karya Konstruksi',
    type: 'Full-Stack Web',
    period: 'Dec 2025 — Feb 2026',
    location: 'Jakarta Selatan',
    link: 'https://reguler.lspgatensi.id/login',
    points: [
      'Built a certification assessment management system using Laravel 10 with Tailwind CSS.',
      'Features: participant data, payment confirmation, identity verification, and certificate generation.',
      'Responsible for VPS deployment on Biznet Gio and server configuration.'
    ],
    tech: ['Laravel 10', 'TailwindCSS', 'PHP', 'MySQL', 'VPS', 'Biznet Gio']
  },
  {
    title: 'EV Bus SureDrive Web',
    company: 'PT. Solu Filantropi Teknologi',
    type: 'Full-Stack Web',
    period: 'Aug 2025 — Oct 2025',
    location: 'Jakarta Selatan',
    link: 'https://api.suredrive-adas.smartpamobvit.id/',
    points: [
      'Built a dashboard to monitor electric vehicles integrated with Teltonika ADAS IoT cameras.',
      'Provides real-time visibility into vehicle activity, driver behavior, and event monitoring.',
      'Frontend with Blade Template + TailwindCSS, backend with Laravel 8.'
    ],
    tech: ['Laravel 8', 'TailwindCSS', 'Blade', 'IoT', 'Real-time', 'MySQL']
  },
  {
    title: 'Alarm System Saras RESTful API',
    company: 'PT. Solu Filantropi Teknologi',
    type: 'Back-End REST API',
    period: 'Jun 2025 — Jul 2025',
    location: 'Jakarta Selatan',
    link: null,
    points: [
      'Developed a RESTful API for an alarm management system using Go and the Fiber framework.',
      'Implemented JWT authentication, GORM for ORM, and PostgreSQL as the database.',
      'Focused on building a structured, secure, and scalable backend service.'
    ],
    tech: ['Go', 'Fiber', 'JWT', 'GORM', 'PostgreSQL']
  }
]
</script>
