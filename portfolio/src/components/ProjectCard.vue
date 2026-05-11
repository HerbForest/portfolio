<template>
  <div class="project-card" :class="{ featured }">
    <div class="project-visual">
      <slot name="visual" />
    </div>
    <div class="project-body">
      <div class="project-type">{{ type }}</div>
      <h3 class="project-title">{{ title }}</h3>
      <p class="project-desc">{{ desc }}</p>
      <div class="project-stack">
        <span class="pill" v-for="tech in stack" :key="tech">{{ tech }}</span>
      </div>
      <div class="project-links" v-if="links && links.length">
        <a v-for="link in links" :key="link.label" :href="link.href" class="link-btn">
          <svg v-if="link.icon === 'globe'" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <path d="M6 1a5 5 0 100 10A5 5 0 006 1zM1.5 6h9M6 1c-1.5 1.8-2 3.8-2 5s.5 3.2 2 5M6 1c1.5 1.8 2 3.8 2 5s-.5 3.2-2 5" stroke="currentColor" stroke-width="1" stroke-linecap="round"/>
          </svg>
          <svg v-if="link.icon === 'github'" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <path d="M6 1C3.24 1 1 3.24 1 6c0 2.21 1.43 4.09 3.41 4.75.25.05.34-.11.34-.24V9.56C3.34 9.85 3.05 9 3.05 9c-.22-.57-.55-.72-.55-.72-.45-.31.03-.3.03-.3.5.03.76.51.76.51.44.76 1.16.54 1.44.41.04-.32.17-.54.31-.66-1.1-.13-2.26-.55-2.26-2.45 0-.54.19-.98.51-1.33-.05-.13-.22-.63.05-1.31 0 0 .42-.13 1.37.51A4.77 4.77 0 016 3.9c.42.002.85.057 1.25.17.95-.64 1.37-.51 1.37-.51.27.68.1 1.18.05 1.31.32.35.51.79.51 1.33 0 1.91-1.16 2.33-2.27 2.45.18.16.34.46.34.93v1.39c0 .13.09.29.34.24C9.57 10.09 11 8.21 11 6c0-2.76-2.24-5-5-5z" fill="currentColor"/>
          </svg>
          {{ link.label }}
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  featured: { type: Boolean, default: false },
  type: { type: String, required: true },
  title: { type: String, required: true },
  desc: { type: String, required: true },
  stack: { type: Array, default: () => [] },
  links: { type: Array, default: () => [] },
})
</script>

<style scoped>
.project-card {
  border: 1px solid rgba(255, 243, 198, 0.08);
  border-radius: var(--radius-lg);
  overflow: hidden;
  background: var(--dark2);
  transition: border-color 0.25s, transform 0.2s;
  cursor: pointer;

  &:hover {
    border-color: rgba(215, 151, 6, 0.3);
    transform: translateY(-3px);
  }

  &.featured {
    grid-column: 1 / -1;
    display: grid;
    grid-template-columns: 1.2fr 1fr;

    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }
}

.project-visual {
  aspect-ratio: 16 / 9;
  position: relative;
  overflow: hidden;
  background: var(--dark3);

  .featured & {
    aspect-ratio: auto;
    min-height: 240px;
  }

  :deep(svg),
  :deep(img) {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: top;
    display: block;
  }
}

.project-body {
  padding: 1.5rem;
}

.project-type {
  font-family: var(--mono);
  font-size: 0.7rem;
  color: var(--gold);
  letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-bottom: 0.6rem;
}

.project-title {
  font-family: var(--serif);
  font-size: 1.4rem;
  color: var(--cream);
  margin-bottom: 0.6rem;
  line-height: 1.2;
}

.project-desc {
  font-size: 0.875rem;
  color: var(--text-muted);
  line-height: 1.7;
  font-weight: 300;
  margin-bottom: 1.25rem;
}

.project-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-bottom: 1.25rem;
}

.project-links {
  display: flex;
  gap: 1rem;
}
</style>
