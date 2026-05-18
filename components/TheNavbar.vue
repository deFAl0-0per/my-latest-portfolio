<template>
  <header
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-500"
    :class="scrolled ? 'bg-dark-900/90 backdrop-blur-xl border-b border-dark-600/50 shadow-xl shadow-black/20' : 'bg-transparent'"
  >
    <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex items-center justify-between h-16">
      <!-- Logo -->
      <a href="#home" class="font-mono text-primary-400 font-bold text-lg hover:text-primary-300 transition-colors">
        &lt;raafa /&gt;
      </a>

      <!-- Desktop Nav -->
      <ul class="hidden md:flex items-center gap-8">
        <li v-for="item in navItems" :key="item.href">
          <a
            :href="item.href"
            class="text-sm font-medium text-gray-400 hover:text-primary-400 transition-colors duration-200 relative group"
            :class="{ 'text-primary-400': activeSection === item.id }"
          >
            <span class="font-mono text-primary-500/60 text-xs mr-1">{{ item.num }}.</span>
            {{ item.label }}
            <span
              class="absolute -bottom-1 left-0 h-px bg-primary-400 transition-all duration-300"
              :class="activeSection === item.id ? 'w-full' : 'w-0 group-hover:w-full'"
            />
          </a>
        </li>
      </ul>

      <!-- Resume Button -->
      <a
        href="mailto:ibra030107@gmail.com"
        class="hidden md:inline-flex items-center gap-2 px-4 py-2 border border-primary-500/50 text-primary-400 hover:text-primary-300 hover:border-primary-400 text-sm font-mono rounded-lg transition-all duration-300 hover:bg-primary-500/10"
      >
        Hire Me
        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
        </svg>
      </a>

      <!-- Mobile Hamburger -->
      <button
        class="md:hidden p-2 text-gray-400 hover:text-primary-400 transition-colors"
        @click="mobileOpen = !mobileOpen"
      >
        <svg v-if="!mobileOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </nav>

    <!-- Mobile Menu -->
    <Transition name="mobile-menu">
      <div
        v-if="mobileOpen"
        class="md:hidden bg-dark-800/95 backdrop-blur-xl border-b border-dark-600/50"
      >
        <ul class="px-4 py-4 flex flex-col gap-4">
          <li v-for="item in navItems" :key="item.href">
            <a
              :href="item.href"
              class="flex items-center gap-3 text-gray-400 hover:text-primary-400 transition-colors py-2"
              :class="{ 'text-primary-400': activeSection === item.id }"
              @click="mobileOpen = false"
            >
              <span class="font-mono text-primary-500/60 text-xs">{{ item.num }}.</span>
              {{ item.label }}
            </a>
          </li>
          <li>
            <a
              href="mailto:ibra030107@gmail.com"
              class="inline-flex items-center gap-2 px-4 py-2 border border-primary-500/50 text-primary-400 text-sm font-mono rounded-lg w-full justify-center mt-2"
              @click="mobileOpen = false"
            >
              Hire Me
            </a>
          </li>
        </ul>
      </div>
    </Transition>
  </header>
</template>

<script setup lang="ts">
const scrolled = ref(false)
const mobileOpen = ref(false)
const activeSection = ref('home')

const navItems = [
  { num: '01', id: 'home',       href: '#home',       label: 'Home' },
  { num: '02', id: 'about',      href: '#about',      label: 'About' },
  { num: '03', id: 'skills',     href: '#skills',     label: 'Skills' },
  { num: '04', id: 'experience', href: '#experience', label: 'Experience' },
  { num: '05', id: 'projects',   href: '#projects',   label: 'Projects' },
  { num: '06', id: 'contact',    href: '#contact',    label: 'Contact' }
]

onMounted(() => {
  window.addEventListener('scroll', () => {
    scrolled.value = window.scrollY > 50

    const sections = navItems.map(i => i.id)
    for (const id of [...sections].reverse()) {
      const el = document.getElementById(id)
      if (el && window.scrollY >= el.offsetTop - 120) {
        activeSection.value = id
        break
      }
    }
  })
})
</script>

<style scoped>
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: all 0.3s ease;
}
.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
