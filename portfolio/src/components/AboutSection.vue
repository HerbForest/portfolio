<script setup>
import { ref, onMounted } from 'vue'

const skillBarsEl = ref(null)
const animated = ref(false)

const stack = [
    { label: 'Framework', name: 'Vue 3' },
    { label: 'Sprog', name: 'JavaScript' },
    { label: 'Database', name: ['Firestore', 'SQLlite'] },
    { label: 'Storage / Auth', name: 'Firebase' },
    { label: 'Styling', name: ['CSS', 'SCSS / BEM'] },
    { label: 'Routing', name: 'Vue Router' },
    { label: 'CI / CD', name: 'GitHub Actions' },
    { label: 'Versionsstyring', name: 'Git' },
    { label: 'Libraries', name: ['sequelize', 'HandleBars'] },
]



onMounted(() => {
    const observer = new IntersectionObserver(
        (entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting) {
                    setTimeout(() => { animated.value = true }, 80)
                    observer.unobserve(entry.target)
                }
            })
        },
        { threshold: 0.3 }
    )
    if (skillBarsEl.value) observer.observe(skillBarsEl.value)
})
</script>

<template>
    <section id="about">
        <div class="about-grid">
            <div>
                <div class="section-label">Om mig</div>
                <h2 class="section-title">Frontend-fokus.<br><em>Backend-nysgerrighed.</em></h2>
                <p class="body-text">
                    Jeg er webudvikler med en <strong>professionsbachelor i webudvikling</strong> og en ægte interesse
                    for hele stacken — ikke kun det der sker i browseren, men også hvordan data struktureres,
                    flows designes og systemer taler sammen.
                </p>
                <p class="body-text">
                    Jeg er <strong>stærk i Vue 3 og moderne JavaScript</strong>, og jeg sætter pris på kode der er
                    let at læse, nem at vedligeholde og bygget med formål. Jeg arbejder komfortabelt med SCSS/BEM,
                    Vue Router og Firebase, og jeg er ikke bange for at stille spørgsmålstegn ved arkitektur og
                    workflow.
                </p>
                <p class="body-text">
                    Jeg leder efter en praktikplads hvor jeg kan lære af erfarne udviklere og
                    arbejde på produkter der betyder noget.
                </p>
            </div>

            <div>
                <div class="section-label">Stack & Teknologier</div>
                <div class="stack-grid">
                    <div class="stack-item" v-for="item in stack" :key="item.label">
                        <div class="stack-item-label">{{ item.label }}</div>
                        <div class="stack-item-name">
                            <span class="stack-tag" v-for="n in [item.name].flat()" :key="n">{{ n }}</span>
                        </div>
                    </div>
                </div>


            </div>
        </div>
    </section>
</template>


<style scoped>
.about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: start;

    @media (max-width: 1024px) {
        grid-template-columns: 1fr;
        gap: 3rem;
    }
}

.stack-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.75rem;
    margin-top: 1.5rem;
}

.stack-item {
    padding: 1rem 1.25rem;
    border: 1px solid rgba(255, 243, 198, 0.08);
    border-radius: var(--radius);
    background: rgba(255, 243, 198, 0.02);
    transition: border-color 0.2s, background 0.2s;

    &:hover {
        border-color: rgba(215, 151, 6, 0.3);
        background: rgba(215, 151, 6, 0.04);
    }
}

.stack-item-label {
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 0.08em;
    margin-bottom: 0.25rem;
}

.stack-item-name {
    display: flex;
    flex-wrap: wrap;
    gap: 0.35rem;
    align-items: center;
}

.stack-tag {
    font-size: 0.8rem;
    font-family: var(--mono);
    padding: 0.15rem 0.5rem;
    border-radius: 2px;
    background: rgba(215, 151, 6, 0.08);
    border: 1px solid rgba(215, 151, 6, 0.2);
    color: var(--gold-light);
}

.skill-bars {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.skill-bar-row {
    display: flex;
    flex-direction: column;
    gap: 0.3rem;
}

.skill-bar-label {
    display: flex;
    justify-content: space-between;
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--text-muted);
}

.skill-bar-track {
    height: 3px;
    background: rgba(255, 243, 198, 0.07);
    border-radius: 2px;
    overflow: hidden;
}

.skill-bar-fill {
    height: 100%;
    background: var(--gold);
    border-radius: 2px;
    transition: width 1s ease;
}
</style>
