<template>
    <section id="projekter">
        <div class="projects-header">
            <div>
                <div class="section-label">Projekter</div>
                <h2 class="section-title">Valgte <em>Projekter</em></h2>
            </div>
        </div>

        <div class="projects-grid">
            <!-- Milton House — featured -->
            <ProjectCard :featured="true" type="Semesterprojekt · Akademisk" title="Milton House"
                desc="Webapplikation til forbedret kommunikation og transparens mellem byggeklienter og byggeledere. Indeholder rollebaseret routing, Gantt-diagram til projektplanlægning, billedgalleri med Firebase Storage og realtidsopdateringer via Firestore."
                :stack="['Vue 3', 'Firebase', 'Firestore', 'Vue Router', 'SCSS/BEM', 'GitHub Actions', 'JSDoc']"
                :links="[{ label: 'Live demo', icon: 'globe', href: '#' }, { label: 'GitHub', icon: 'github', href: '#' }]">
                <template #visual>
                    <svg viewBox="0 0 500 340" xmlns="http://www.w3.org/2000/svg" style="background:#0d3f35;">
                        <rect width="500" height="340" fill="#0d3f35" />
                        <rect x="30" y="30" width="440" height="280" rx="8" fill="rgba(9,48,40,0.7)"
                            stroke="rgba(215,151,6,0.15)" stroke-width="1" />
                        <rect x="30" y="30" width="440" height="36" rx="8" fill="rgba(215,151,6,0.08)" />
                        <text x="50" y="53" font-family="monospace" font-size="11" fill="#D79706"
                            opacity="0.9">milton-house</text>
                        <text x="200" y="53" font-family="monospace" font-size="10" fill="#7ab89e">Byggeleder</text>
                        <text x="340" y="53" font-family="monospace" font-size="10" fill="#7ab89e">Tidslinje</text>
                        <rect x="50" y="84" width="80" height="14" rx="2" fill="rgba(215,151,6,0.15)"
                            stroke="rgba(215,151,6,0.3)" stroke-width="0.5" />
                        <text x="55" y="95" font-family="monospace" font-size="9" fill="#7ab89e">Jordarbejde</text>
                        <rect x="145" y="84" width="120" height="14" rx="2" fill="#D79706" opacity="0.7" />
                        <rect x="50" y="108" width="80" height="14" rx="2" fill="rgba(215,151,6,0.15)"
                            stroke="rgba(215,151,6,0.3)" stroke-width="0.5" />
                        <text x="55" y="119" font-family="monospace" font-size="9" fill="#7ab89e">Fundament</text>
                        <rect x="275" y="108" width="90" height="14" rx="2" fill="#D79706" opacity="0.5" />
                        <rect x="50" y="132" width="80" height="14" rx="2" fill="rgba(215,151,6,0.15)"
                            stroke="rgba(215,151,6,0.3)" stroke-width="0.5" />
                        <text x="55" y="143" font-family="monospace" font-size="9" fill="#7ab89e">Råhus</text>
                        <rect x="375" y="132" width="70" height="14" rx="2" fill="#D79706" opacity="0.3" />
                        <rect x="50" y="156" width="80" height="14" rx="2" fill="rgba(215,151,6,0.15)"
                            stroke="rgba(215,151,6,0.3)" stroke-width="0.5" />
                        <text x="55" y="167" font-family="monospace" font-size="9" fill="#7ab89e">Tagkonstruktion</text>
                        <rect x="50" y="195" width="60" height="18" rx="3" fill="rgba(19,79,66,0.8)"
                            stroke="rgba(215,151,6,0.2)" stroke-width="0.5" />
                        <text x="55" y="208" font-family="monospace" font-size="8" fill="#D79706">Vue 3</text>
                        <rect x="118" y="195" width="70" height="18" rx="3" fill="rgba(19,79,66,0.8)"
                            stroke="rgba(215,151,6,0.2)" stroke-width="0.5" />
                        <text x="123" y="208" font-family="monospace" font-size="8" fill="#D79706">Firestore</text>
                        <rect x="196" y="195" width="80" height="18" rx="3" fill="rgba(19,79,66,0.8)"
                            stroke="rgba(215,151,6,0.2)" stroke-width="0.5" />
                        <text x="201" y="208" font-family="monospace" font-size="8" fill="#D79706">Vue Router</text>
                        <rect x="284" y="195" width="70" height="18" rx="3" fill="rgba(19,79,66,0.8)"
                            stroke="rgba(215,151,6,0.2)" stroke-width="0.5" />
                        <text x="289" y="208" font-family="monospace" font-size="8" fill="#D79706">SCSS/BEM</text>
                        <circle cx="420" cy="200" r="20" fill="rgba(215,151,6,0.08)" stroke="rgba(215,151,6,0.2)"
                            stroke-width="1" />
                        <text x="412" y="205" font-family="monospace" font-size="10" fill="#D79706">FB</text>
                        <line x1="50" y1="250" x2="450" y2="250" stroke="rgba(255,243,198,0.06)" stroke-width="1" />
                        <text x="50" y="270" font-family="monospace" font-size="9" fill="#7ab89e"
                            opacity="0.7">Semester-case projekt · Gruppe · 2024–2025</text>
                    </svg>
                </template>
            </ProjectCard>

            <!-- TensorFlow.js -->
            <ProjectCard type="Lab-opgave · ML" title="TensorFlow.js — ML i browseren"
                desc="Implementering af lineær regression (husprisprediktion) og binær klassifikation (vandfront-analyse) med TensorFlow.js. Debugging på lav niveau med Tensor API."
                :stack="['TensorFlow.js', 'JavaScript', 'Data preprocessing']">
                <template #visual>
                    <svg viewBox="0 0 260 140" xmlns="http://www.w3.org/2000/svg"
                        style="width:100%;background:#0a2e26;">
                        <rect width="260" height="140" fill="#0a2e26" rx="4" />
                        <circle cx="30" cy="30" r="8" fill="none" stroke="#D79706" stroke-width="1.2" opacity="0.7" />
                        <circle cx="30" cy="70" r="8" fill="none" stroke="#D79706" stroke-width="1.2" opacity="0.7" />
                        <circle cx="30" cy="110" r="8" fill="none" stroke="#D79706" stroke-width="1.2" opacity="0.7" />
                        <circle cx="90" cy="20" r="8" fill="rgba(215,151,6,0.15)" stroke="#D79706" stroke-width="1.2"
                            opacity="0.8" />
                        <circle cx="90" cy="50" r="8" fill="rgba(215,151,6,0.15)" stroke="#D79706" stroke-width="1.2"
                            opacity="0.8" />
                        <circle cx="90" cy="80" r="8" fill="rgba(215,151,6,0.15)" stroke="#D79706" stroke-width="1.2"
                            opacity="0.8" />
                        <circle cx="90" cy="110" r="8" fill="rgba(215,151,6,0.15)" stroke="#D79706" stroke-width="1.2"
                            opacity="0.8" />
                        <circle cx="150" cy="40" r="8" fill="rgba(215,151,6,0.3)" stroke="#D79706" stroke-width="1.5"
                            opacity="0.9" />
                        <circle cx="150" cy="80" r="8" fill="rgba(215,151,6,0.3)" stroke="#D79706" stroke-width="1.5"
                            opacity="0.9" />
                        <circle cx="210" cy="60" r="8" fill="#D79706" opacity="0.8" />
                        <line x1="38" y1="30" x2="82" y2="20" stroke="rgba(215,151,6,0.2)" stroke-width="0.8" />
                        <line x1="38" y1="30" x2="82" y2="50" stroke="rgba(215,151,6,0.2)" stroke-width="0.8" />
                        <line x1="38" y1="70" x2="82" y2="50" stroke="rgba(215,151,6,0.2)" stroke-width="0.8" />
                        <line x1="38" y1="70" x2="82" y2="80" stroke="rgba(215,151,6,0.2)" stroke-width="0.8" />
                        <line x1="38" y1="110" x2="82" y2="80" stroke="rgba(215,151,6,0.2)" stroke-width="0.8" />
                        <line x1="38" y1="110" x2="82" y2="110" stroke="rgba(215,151,6,0.2)" stroke-width="0.8" />
                        <line x1="98" y1="20" x2="142" y2="40" stroke="rgba(215,151,6,0.3)" stroke-width="0.8" />
                        <line x1="98" y1="50" x2="142" y2="40" stroke="rgba(215,151,6,0.3)" stroke-width="0.8" />
                        <line x1="98" y1="80" x2="142" y2="80" stroke="rgba(215,151,6,0.3)" stroke-width="0.8" />
                        <line x1="98" y1="110" x2="142" y2="80" stroke="rgba(215,151,6,0.3)" stroke-width="0.8" />
                        <line x1="158" y1="40" x2="202" y2="60" stroke="rgba(215,151,6,0.5)" stroke-width="1" />
                        <line x1="158" y1="80" x2="202" y2="60" stroke="rgba(215,151,6,0.5)" stroke-width="1" />
                        <text x="10" y="130" font-family="monospace" font-size="8" fill="#7ab89e"
                            opacity="0.7">TensorFlow.js · Linear regression · Binary classification</text>
                    </svg>
                </template>
            </ProjectCard>

            <!-- Dexpok -->
            <ProjectCard
                type="Web App · Pokémon"
                title="Dexpok"
                desc="Pokémon-kortpung der synkroniserer den realtidsværdi af dine kort via et eksternt API. Tilføj dine kort og se den samlede porteføljeværdi opdateret live — synkroniseret på tværs af enheder med Firestore."
                :stack="['Vue 3', 'Firestore', 'REST API', 'Firebase Hosting', 'Vite']"
                :links="[{ label: 'Live demo', icon: 'globe', href: 'https://dexpok.web.app/' }]"
            >
                <template #visual>
                    <img
                        :src="`https://s0.wordpress.com/mshots/v1/${encodeURIComponent('https://dexpok.web.app/')}?w=640&h=400`"
                        alt="Dexpok screenshot"
                        loading="lazy"
                    />
                </template>
            </ProjectCard>
        </div>
    </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'
</script>

<style scoped>
section {
    max-width: 1100px;
    margin: 0 auto;
    padding: 6rem 4rem;
}

.projects-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 3rem;
}

.projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;

    @media (max-width: 640px) {
        grid-template-columns: 1fr;
    }
}
</style>
