<template>
  <div>
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ExperienceSection />
    <ProjectsSection />
    <EducationSection />
    <ContactSection />
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'Raafa Ibra Ardhefran – Full-Stack Developer',
  meta: [
    { name: 'description', content: 'Portfolio of Raafa Ibra Ardhefran – Full-Stack Developer from Jakarta, Indonesia. Specialized in Laravel, Go, Nuxt.js, and Next.js.' }
  ]
})

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('revealed')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.1 }
  )

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el))
})
</script>
