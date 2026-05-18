<template>
  <section id="skills" class="py-24 relative overflow-hidden">
    <div class="absolute left-0 top-1/2 -translate-y-1/2 w-96 h-96 bg-primary-500/5 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16 reveal">
        <p class="section-subtitle">// my toolbox</p>
        <h2 class="section-title">Skills & Technologies</h2>
        <p class="text-gray-400 max-w-xl mx-auto mt-3">
          Technologies I use to build scalable, modern web applications from frontend to backend.
        </p>
      </div>

      <!-- Category Tabs -->
      <div class="flex flex-wrap justify-center gap-3 mb-10 reveal">
        <button
          v-for="cat in categories"
          :key="cat.id"
          @click="activeCategory = cat.id"
          class="px-4 py-2 rounded-xl text-sm font-medium transition-all duration-300"
          :class="activeCategory === cat.id
            ? 'bg-primary-500 text-dark-900 shadow-lg shadow-primary-500/30'
            : 'border border-dark-600 text-gray-400 hover:text-primary-400 hover:border-primary-500/40'"
        >
          {{ cat.label }}
        </button>
      </div>

      <!-- Skills Grid -->
      <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4 reveal">
        <TransitionGroup name="skill-card">
          <div
            v-for="skill in filteredSkills"
            :key="skill.name"
            class="card group flex flex-col gap-3 hover:scale-105 hover:glow transition-all duration-300 cursor-default"
          >
            <div class="flex items-center justify-between">
              <div class="flex items-center gap-3">
                <div class="w-9 h-9 rounded-lg flex items-center justify-center text-xl" :class="skill.bg">
                  <img v-if="skill.icon.startsWith('/')" :src="skill.icon" :alt="skill.name" class="w-6 h-6 object-contain" />
                  <span v-else>{{ skill.icon }}</span>
                </div>
                <div>
                  <div class="text-white text-sm font-semibold">{{ skill.name }}</div>
                  <div class="text-xs" :class="levelColor(skill.level)">{{ skill.level }}</div>
                </div>
              </div>
            </div>

            <!-- Progress bar -->
            <div class="h-1.5 rounded-full bg-dark-600 overflow-hidden">
              <div
                class="h-1.5 rounded-full transition-all duration-700"
                :class="barColor(skill.level)"
                :style="`width: ${levelPercent(skill.level)}%`"
              />
            </div>
          </div>
        </TransitionGroup>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const activeCategory = ref('all')

const categories = [
  { id: 'all',      label: 'All' },
  { id: 'backend',  label: 'Backend' },
  { id: 'frontend', label: 'Frontend' },
  { id: 'database', label: 'Database' },
  { id: 'tools',    label: 'Tools & Other' }
]

const skills = [
  { name: 'Laravel 10',     level: 'Advanced',      icon: '/images/logos/laravel-logo.png', bg: 'bg-red-500/10',     cat: 'backend' },
  { name: 'Go Fiber / Gin', level: 'Intermediate',  icon: '/images/logos/go-logo.png', bg: 'bg-cyan-500/10',    cat: 'backend' },
  { name: 'PHP',            level: 'Advanced',      icon: '/images/logos/php-logo.png', bg: 'bg-violet-500/10',  cat: 'backend' },
  { name: 'Python',         level: 'Intermediate',  icon: '/images/logos/python-logo.png', bg: 'bg-yellow-500/10',  cat: 'backend' },
  { name: 'RESTful API',    level: 'Intermediate',  icon: '/images/logos/rest-api-logo.png', bg: 'bg-orange-500/10',  cat: 'backend' },
  { name: 'Nuxt.js / Vue',  level: 'Beginner',      icon: '/images/logos/nuxt-logo.png', bg: 'bg-green-500/10',   cat: 'frontend' },
  { name: 'Next.js',        level: 'Beginner',      icon: '/images/logos/nexjs-logo.svg', bg: 'bg-white',    cat: 'frontend' },
  { name: 'React',          level: 'Beginner',      icon: '/images/logos/react-logo.png', bg: 'bg-blue-500/10',    cat: 'frontend' },
  { name: 'JavaScript',     level: 'Intermediate',  icon: '/images/logos/javascript-logo.png', bg: 'bg-yellow-500/10',  cat: 'frontend' },
  { name: 'TailwindCSS',    level: 'Intermediate',  icon: '/images/logos/tailwindcss-logo.png', bg: 'bg-teal-500/10',    cat: 'frontend' },
  { name: 'AJAX',           level: 'Beginner',      icon: '/images/logos/ajax-logo.jpg', bg: 'bg-blue-500/10',    cat: 'frontend' },
  { name: 'Responsive Web', level: 'Intermediate',  icon: '/images/logos/responsive-logo.png', bg: 'bg-pink-500/10',    cat: 'frontend' },
  { name: 'PostgreSQL',     level: 'Intermediate',  icon: '/images/logos/postgresql-logo.png', bg: 'bg-blue-500/10',    cat: 'database' },
  { name: 'MySQL',          level: 'Intermediate',  icon: '/images/logos/mysql-logo.png', bg: 'bg-orange-500/10',  cat: 'database' },
  { name: 'MongoDB',        level: 'Beginner',      icon: '/images/logos/mongodb-logo.png', bg: 'bg-green-500/10',   cat: 'database' },
  { name: 'Git',            level: 'Intermediate',  icon: '/images/logos/github-logo.png', bg: 'bg-white',  cat: 'tools' },
  { name: 'Docker',         level: 'Beginner',      icon: '/images/logos/docker-logo.png', bg: 'bg-blue-500/10',    cat: 'tools' },
  { name: 'Machine Learning', level: 'Beginner',    icon: '/images/logos/scikit-learn-logo.png', bg: 'bg-purple-500/10',  cat: 'tools' },
]

const filteredSkills = computed(() =>
  activeCategory.value === 'all'
    ? skills
    : skills.filter(s => s.cat === activeCategory.value)
)

function levelPercent(level: string) {
  return { 'Advanced': 90, 'Intermediate': 65, 'Beginner': 35 }[level] ?? 50
}

function levelColor(level: string) {
  return {
    'Advanced':     'text-primary-400',
    'Intermediate': 'text-blue-400',
    'Beginner':     'text-gray-500'
  }[level] ?? 'text-gray-400'
}

function barColor(level: string) {
  return {
    'Advanced':     'bg-gradient-to-r from-primary-500 to-teal-400',
    'Intermediate': 'bg-gradient-to-r from-blue-500 to-cyan-400',
    'Beginner':     'bg-gradient-to-r from-gray-600 to-gray-500'
  }[level] ?? 'bg-primary-500'
}
</script>

<style scoped>
.skill-card-enter-active,
.skill-card-leave-active {
  transition: all 0.3s ease;
}
.skill-card-enter-from {
  opacity: 0;
  transform: scale(0.9);
}
.skill-card-leave-to {
  opacity: 0;
  transform: scale(0.9);
}
</style>
