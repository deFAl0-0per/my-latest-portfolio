<template>
  <section id="contact" class="py-24 relative overflow-hidden">
    <div class="absolute inset-0 bg-[linear-gradient(rgba(20,184,166,0.02)_1px,transparent_1px),linear-gradient(90deg,rgba(20,184,166,0.02)_1px,transparent_1px)] bg-[size:60px_60px]" />
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[400px] bg-primary-500/8 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="text-center mb-16 reveal">
        <p class="section-subtitle">// let's work together</p>
        <h2 class="section-title">Get In Touch</h2>
        <p class="text-gray-400 max-w-xl mx-auto mt-3">
          Have a project in mind or just want to say hello? My inbox is always open.
          I'll get back to you as soon as possible!
        </p>
      </div>

      <div class="grid md:grid-cols-2 gap-8 reveal">
        <!-- Contact Info -->
        <div class="space-y-6">

          <!-- Email -->
          <div class="card group hover:border-primary-500/40 hover:scale-[1.02] transition-all duration-300">
            <a href="mailto:ibra030107@gmail.com" class="flex items-center gap-4">
              <div class="w-12 h-12 rounded-xl bg-primary-500/10 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-primary-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                </svg>
              </div>
              <div>
                <div class="text-gray-500 text-xs font-mono mb-0.5">Email</div>
                <div class="text-white font-medium group-hover:text-primary-400 transition-colors">ibra030107@gmail.com</div>
              </div>
              <div class="ml-auto text-gray-600 group-hover:text-primary-400 transition-colors">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
                </svg>
              </div>
            </a>
          </div>

          <!-- WhatsApp -->
          <div class="card group hover:border-primary-500/40 hover:scale-[1.02] transition-all duration-300">
            <a href="https://wa.me/6285692945163" target="_blank" class="flex items-center gap-4">
              <div class="w-12 h-12 rounded-xl bg-green-500/10 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                </svg>
              </div>
              <div>
                <div class="text-gray-500 text-xs font-mono mb-0.5">WhatsApp</div>
                <div class="text-white font-medium group-hover:text-primary-400 transition-colors">+62 856 9294 5163</div>
              </div>
              <div class="ml-auto text-gray-600 group-hover:text-primary-400 transition-colors">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
                </svg>
              </div>
            </a>
          </div>

          <!-- Location -->
          <div class="card">
            <div class="flex items-start gap-4">
              <div class="w-12 h-12 rounded-xl bg-red-500/10 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-red-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                </svg>
              </div>
              <div>
                <div class="text-gray-500 text-xs font-mono mb-0.5">Location</div>
                <div class="text-white font-medium">Jakarta Timur, Indonesia</div>
                <div class="text-gray-400 text-sm mt-0.5">Jl. Bhakti 1 RT 016 RW 008, Pulogebang Cakung, 13950</div>
              </div>
            </div>
          </div>
        </div>

        <!-- CTA Card -->
        <div class="card bg-gradient-to-br from-primary-500/15 to-teal-500/5 border-primary-500/30 flex flex-col justify-center items-center text-center gap-6 p-8">
          <div class="text-5xl">👋</div>
          <div>
            <h3 class="text-white font-bold text-xl mb-2">Open for Opportunities</h3>
            <p class="text-gray-400 text-sm leading-relaxed">
              I'm currently available for freelance projects, full-time positions, and internship extensions.
              Let's build something amazing together!
            </p>
          </div>
          <div class="flex flex-col gap-3 w-full">
            <a href="mailto:ibra030107@gmail.com" class="btn-primary justify-center">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
              </svg>
              Send Email
            </a>
            <a href="https://wa.me/6285692945163" target="_blank" class="btn-outline justify-center">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
              </svg>
              +62 856 9294 5163
            </a>
          </div>

          <div class="flex items-center gap-2 text-sm text-gray-400">
            <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse" />
            Available for new projects
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
