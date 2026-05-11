<template>
  <section>
    <div class="section-label">Interesser & Tilgang</div>
    <h2 class="section-title">Mere end <em>UI</em></h2>

    <div class="interests-grid">
      <div class="interest-card" v-for="item in interests" :key="item.title">
        <svg class="interest-icon" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" v-html="item.iconPath"></svg>
        <div class="interest-title">{{ item.title }}</div>
        <p class="interest-desc">{{ item.desc }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const interests = [
  {
    title: 'Datastruktur',
    desc: 'Jeg tænker bevidst over hvordan data modelleres i Firestore — collections, subcollections, denormalisering og realtime updates.',
    iconPath: `
      <rect x="5" y="25" width="30" height="4" rx="2" fill="currentColor" opacity="0.15"/>
      <rect x="5" y="18" width="20" height="4" rx="2" fill="currentColor" opacity="0.3"/>
      <rect x="5" y="11" width="25" height="4" rx="2" fill="currentColor" opacity="0.6"/>
      <rect x="5" y="4" width="15" height="4" rx="2" fill="currentColor"/>
    `,
  },
  {
    title: 'Komponentarkitektur',
    desc: 'Slots, composables og BEM-SCSS. Jeg går op i at bygge komponenter der er fleksible nok til at genbruges uden at blive abstraherede til ukendelighed.',
    iconPath: `
      <circle cx="8" cy="20" r="4" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="32" cy="10" r="4" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="32" cy="30" r="4" stroke="currentColor" stroke-width="1.5"/>
      <line x1="12" y1="18" x2="28" y2="12" stroke="currentColor" stroke-width="1.2" opacity="0.6"/>
      <line x1="12" y1="22" x2="28" y2="28" stroke="currentColor" stroke-width="1.2" opacity="0.6"/>
    `,
  },
  {
    title: 'Developer Workflow',
    desc: 'CI/CD pipelines, linting, dokumentation og kode-review. Jeg tror på at god infrastruktur er investering, ikke overhead.',
    iconPath: `
      <rect x="5" y="8" width="30" height="20" rx="3" stroke="currentColor" stroke-width="1.5"/>
      <path d="M15 33h10M20 28v5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
      <path d="M12 16l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" opacity="0.7"/>
      <line x1="19" y1="21" x2="27" y2="21" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" opacity="0.7"/>
    `,
  },
]
</script>

<style scoped>
section {
  max-width: 1100px;
  margin: 0 auto;
  padding: 5rem 4rem;
}

.interests-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  margin-top: 3rem;

  @media (max-width: 1024px) { grid-template-columns: repeat(2, 1fr); }
  @media (max-width: 640px)  { grid-template-columns: 1fr; }
}

.interest-card {
  padding: 2rem 1.5rem;
  border: 1px solid rgba(255, 243, 198, 0.08);
  border-radius: var(--radius-lg);
  background: rgba(255, 243, 198, 0.01);
  transition: border-color 0.2s;

  &:hover { border-color: rgba(215, 151, 6, 0.25); }
}

.interest-icon {
  width: 40px;
  height: 40px;
  margin-bottom: 1.25rem;
  color: var(--gold);
}

.interest-title {
  font-family: var(--serif);
  font-size: 1.25rem;
  color: var(--cream);
  margin-bottom: 0.5rem;
}

.interest-desc {
  font-size: 0.875rem;
  color: var(--text-muted);
  line-height: 1.7;
  font-weight: 300;
}
</style>
