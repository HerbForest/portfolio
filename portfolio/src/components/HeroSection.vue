<template>
  <div class="hero" id="top">
    <div class="hero-bg" aria-hidden="true">
      <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid slice">
        <defs>
          <pattern id="grid" width="60" height="60" patternUnits="userSpaceOnUse">
            <path d="M 60 0 L 0 0 0 60" fill="none" stroke="#FFF3C6" stroke-width="0.5"/>
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#grid)"/>
        <circle cx="900" cy="200" r="300" fill="none" stroke="#D79706" stroke-width="0.5" opacity="0.3"/>
        <circle cx="900" cy="200" r="200" fill="none" stroke="#D79706" stroke-width="0.5" opacity="0.2"/>
        <circle cx="150" cy="600" r="200" fill="none" stroke="#D79706" stroke-width="0.5" opacity="0.15"/>
      </svg>
    </div>

    <div class="hero-inner">
      <div class="hero-eyebrow">Søger praktikplads — Frontend</div>
      <h1 class="hero-name">
        Valdemar<br>
        <em>Web Developer</em>
      </h1>
      <p class="hero-subtitle">
        Professionsbachelor i webudvikling. Bygger moderne, skalerbare applikationer med
        <strong>Vue 3</strong>, <strong>JavaScript</strong> og <strong>Firestore</strong>
        — med sans for datastruktur, clean code og brugeroplevelse.
      </p>
      <div class="hero-tags">
        <span class="tag" v-for="tag in tags" :key="tag">{{ tag }}</span>
      </div>
      <a href="#kontakt" class="hero-cta">
        Tag kontakt
        <svg viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </a>
    </div>

    <div class="scroll-hint" aria-hidden="true">
      <span>scroll</span>
      <svg viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M7 2v10M3 8l4 4 4-4" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>
  </div>
</template>

<script setup>
const tags = ['Vue 3', 'JavaScript', 'Firebase', 'Firestore', 'SCSS / BEM', 'Vue Router', 'REST APIs', 'Git / CI-CD']
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-top: 8rem;
  padding-bottom: 4rem;
  position: relative;
  max-width: 100%;
}

.hero-bg {
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  z-index: -1;
  overflow: hidden;

  svg {
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    opacity: 0.07;
  }
}

.hero-eyebrow {
  font-family: var(--mono);
  font-size: 0.8rem;
  color: var(--gold);
  letter-spacing: 0.15em;
  text-transform: uppercase;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.75rem;

  &::before {
    content: '';
    display: block;
    width: 2rem;
    height: 1px;
    background: var(--gold);
  }
}

.hero-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 4rem;

  @media (max-width: 1024px) { padding: 0 2.5rem; }
  @media (max-width: 640px)  { padding: 0 1.5rem; }
}

.hero-name {
  font-family: var(--serif);
  font-size: clamp(3.5rem, 8vw, 7rem);
  line-height: 1.0;
  letter-spacing: -0.02em;
  color: var(--cream);
  margin-bottom: 0.25rem;

  em {
    font-style: italic;
    color: var(--gold);
  }
}

.hero-subtitle {
  font-size: 1.1rem;
  color: var(--text-muted);
  font-weight: 300;
  margin-bottom: 3rem;
  max-width: 520px;
  line-height: 1.8;

  strong {
    color: var(--cream);
    font-weight: 500;
  }
}

.hero-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
  margin-bottom: 3.5rem;
}

.hero-cta {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  background: var(--gold);
  color: var(--dark);
  font-family: var(--sans);
  font-size: 0.9rem;
  font-weight: 500;
  padding: 0.85rem 2rem;
  border-radius: 2px;
  letter-spacing: 0.04em;
  transition: background 0.2s, transform 0.15s;

  &:hover { background: var(--gold-light); transform: translateY(-1px); }

  svg { width: 16px; height: 16px; }
}

.scroll-hint {
  position: absolute;
  bottom: 2.5rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  color: var(--text-muted);
  font-family: var(--mono);
  font-size: 0.7rem;
  letter-spacing: 0.1em;
  animation: bounce 2s ease-in-out infinite;

  svg { width: 14px; opacity: 0.6; }
}

@keyframes bounce {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(6px); }
}
</style>
