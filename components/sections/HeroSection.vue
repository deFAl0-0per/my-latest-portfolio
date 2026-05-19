<template>
  <section id="home" class="relative min-h-screen flex items-center justify-center overflow-hidden pt-16">
    <!-- Animated background grid -->
    <div class="absolute inset-0 bg-[linear-gradient(rgba(20,184,166,0.03)_1px,transparent_1px),linear-gradient(90deg,rgba(20,184,166,0.03)_1px,transparent_1px)] bg-[size:60px_60px]" />

    <!-- Floating blobs -->
    <div class="absolute top-20 right-10 w-96 h-96 bg-primary-500/10 rounded-full blur-3xl animate-float pointer-events-none" />
    <div class="absolute bottom-20 left-10 w-80 h-80 bg-indigo-500/8 rounded-full blur-3xl animate-float pointer-events-none" style="animation-delay: -3s" />
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-primary-500/5 rounded-full blur-3xl pointer-events-none" />

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
      <div class="grid lg:grid-cols-2 gap-12 items-center">

        <!-- Left Content -->
        <div class="space-y-6">
          <div class="inline-flex items-center gap-2 px-4 py-2 bg-primary-500/10 border border-primary-500/20 rounded-full text-primary-400 text-sm font-mono animate-fade-in">
            <span class="w-2 h-2 bg-primary-400 rounded-full animate-pulse" />
            Available for work
          </div>

          <h1 class="animate-fade-up animate-delay-100">
            <span class="block text-gray-400 text-lg font-mono mb-2">Hi, I'm</span>
            <span class="block text-4xl sm:text-5xl lg:text-6xl font-black text-white leading-tight">
              Raafa Ibra
            </span>
            <span class="block text-4xl sm:text-5xl lg:text-6xl font-black leading-tight gradient-text">
              Ardhefran
            </span>
          </h1>

          <div class="flex items-center gap-3 animate-fade-up animate-delay-200">
            <div class="h-px w-8 bg-primary-500" />
            <p class="text-xl text-gray-300 font-medium">
              Full-Stack Developer
            </p>
          </div>

          <p class="text-gray-400 leading-relaxed max-w-lg animate-fade-up animate-delay-300">
            IT enthusiast with the ability to conceptualize and transform ideas into functional
            websites and applications. Skilled in <span class="text-primary-400">PHP, Go, Python, JavaScript</span>
            with frameworks like <span class="text-primary-400">Laravel, Go Fiber, and Nuxt.js</span>.
          </p>

          <!-- Tech Stack -->
          <div class="flex flex-wrap gap-2 animate-fade-up animate-delay-400">
            <span v-for="tech in techStack" :key="tech" class="tag">{{ tech }}</span>
          </div>

          <!-- CTA Buttons -->
          <div class="flex flex-wrap gap-4 animate-fade-up animate-delay-500">
            <a href="#projects" class="btn-primary">
              View My Work
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
              </svg>
            </a>
            <a href="#contact" class="btn-outline">
              Get In Touch
            </a>
          </div>

          <!-- Social Links -->
          <div class="flex gap-4 animate-fade-up animate-delay-600">
            <a href="tel:+6285692945163" class="social-link" title="WhatsApp">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
              </svg>
            </a>
            <a href="mailto:ibra030107@gmail.com" class="social-link" title="Email">
              <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
            </a>
            <a href="https://github.com/deFAl0-0per" class="social-link" title="GitHub" target="_blank">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
            </a>
          </div>
        </div>

        <!-- Right - Avatar / Code Card -->
        <div class="hidden lg:flex justify-center items-center animate-slide-right animate-delay-300">
          <div class="relative">
            <!-- Rotating ring -->
            <div class="absolute inset-0 rounded-full border border-primary-500/20 animate-spin-slow" />
            <div class="absolute inset-4 rounded-full border border-primary-500/10 animate-spin-slow" style="animation-direction: reverse; animation-duration: 15s" />

            <!-- Main card -->
            <div class="relative w-80 h-80 rounded-2xl bg-dark-800 border border-dark-600 glow overflow-hidden">
              <!-- Code-like UI -->
              <div class="p-6 font-mono text-sm h-full flex flex-col">
                <div class="flex items-center gap-2 mb-4">
                  <div class="w-3 h-3 rounded-full bg-red-500/70" />
                  <div class="w-3 h-3 rounded-full bg-yellow-500/70" />
                  <div class="w-3 h-3 rounded-full bg-green-500/70" />
                  <span class="ml-2 text-gray-500 text-xs">developer.ts</span>
                </div>
                <div class="flex-1 space-y-2 text-xs leading-relaxed">
                  <div><span class="text-purple-400">const</span> <span class="text-blue-300">developer</span> <span class="text-gray-400">= {</span></div>
                  <div class="ml-4"><span class="text-green-300">name</span><span class="text-gray-400">:</span> <span class="text-amber-300">"Raafa Ibra"</span><span class="text-gray-400">,</span></div>
                  <div class="ml-4"><span class="text-green-300">role</span><span class="text-gray-400">:</span> <span class="text-amber-300">"Full-Stack Dev"</span><span class="text-gray-400">,</span></div>
                  <div class="ml-4"><span class="text-green-300">location</span><span class="text-gray-400">:</span> <span class="text-amber-300">"Jakarta, ID"</span><span class="text-gray-400">,</span></div>
                  <div class="ml-4"><span class="text-green-300">skills</span><span class="text-gray-400">: [</span></div>
                  <div class="ml-8"><span class="text-amber-300">"Laravel"</span><span class="text-gray-400">,</span></div>
                  <div class="ml-8"><span class="text-amber-300">"Go Gin/Fiber"</span><span class="text-gray-400">,</span></div>
                  <div class="ml-8"><span class="text-amber-300">"Nuxt.js"</span><span class="text-gray-400">,</span></div>
                  <div class="ml-8"><span class="text-amber-300">"Next.js"</span></div>
                  <div class="ml-4"><span class="text-gray-400">],</span></div>
                  <div class="ml-4"><span class="text-green-300">available</span><span class="text-gray-400">:</span> <span class="text-blue-300">true</span></div>
                  <div><span class="text-gray-400">}</span></div>
                  <div class="mt-2 flex items-center gap-1">
                    <span class="text-gray-500">// </span>
                    <span class="text-primary-400 animate-pulse">▊</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Floating badges -->
            <div class="absolute -top-4 -right-4 bg-dark-700 border border-primary-500/30 rounded-xl px-3 py-2 text-xs font-mono text-primary-400 shadow-lg">
              🚀 1+ yrs exp
            </div>
            <div class="absolute -bottom-4 -left-4 bg-dark-700 border border-indigo-500/30 rounded-xl px-3 py-2 text-xs font-mono text-indigo-400 shadow-lg">
              8+ projects
            </div>
          </div>
        </div>

      </div>

      <!-- Scroll indicator -->
      <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 animate-bounce animate-delay-700">
        <span class="text-gray-500 text-xs font-mono">scroll</span>
        <svg class="w-4 h-4 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
        </svg>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const techStack = ['Laravel', 'Go Fiber', 'Nuxt.js', 'Next.js', 'PostgreSQL', 'TailwindCSS']
</script>

<style scoped>
.social-link {
  @apply w-10 h-10 flex items-center justify-center rounded-xl border border-dark-600 text-gray-500 hover:text-primary-400 hover:border-primary-500/50 transition-all duration-300 hover:-translate-y-1;
}
</style>
