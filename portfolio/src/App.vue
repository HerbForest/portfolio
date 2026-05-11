<script setup>
import AppNav from '@/components/AppNav.vue'
import HeroSection from '@/components/HeroSection.vue'
import WordPressSection from '@/components/WordPressSection.vue'
import AboutSection from '@/components/AboutSection.vue'
import ProjectsSection from '@/components/ProjectsSection.vue'
import InterestsSection from '@/components/InterestsSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import AppFooter from '@/components/AppFooter.vue'
</script>

<template>
    <AppNav />
    <main>
        <HeroSection />
        <hr class="divider">
        <WordPressSection />
        <hr class="divider">
        <AboutSection />
        <hr class="divider">
        <ProjectsSection />
        <hr class="divider">
        <InterestsSection />
        <hr class="divider">
        <ContactSection />
    </main>
    <AppFooter />
</template>
