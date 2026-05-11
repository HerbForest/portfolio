<script setup>
const sites = [
    { name: 'Nadine Hammele', url: 'https://www.nadinehammele.de/', tld: '.de' },
    { name: 'Anton Nootenboom', url: 'https://www.antonnootenboom.nl/', tld: '.nl' },
    { name: 'Michel Verheijden', url: 'https://www.michelverheijden.nl/', tld: '.nl' },
    { name: 'Ile Woien', url: 'https://www.ilewoien.no/', tld: '.no' },
    { name: 'Olof Granström', url: 'https://www.olofgranstrom.se/', tld: '.se' },
    { name: 'Cor Hospes', url: 'https://www.cor-hospes.nl/', tld: '.nl' },
    { name: 'Willem Post', url: 'https://www.willem-post.nl/', tld: '.nl' },
    { name: 'Kathalijn Kalawati', url: 'https://www.kathalijnkalawati.nl/', tld: '.nl' },
    { name: 'Oliver Straubel', url: 'https://www.oliver-straubel.de/', tld: '.de' },
]

function screenshotUrl(url) {
    return `https://s0.wordpress.com/mshots/v1/${encodeURIComponent(url)}?w=640&h=400`
}
</script>
<template>
    <section id="wordpress">
        <div class="projects-header">
            <div>
                <div class="section-label">WordPress · Klientarbejde</div>
                <h2 class="section-title">Designede & bygget <em>Onepagesider</em></h2>
            </div>
            <p class="header-note">9 live klientprojekter — design, opbygning og lancering</p>
        </div>

        <div class="wp-grid">
            <a v-for="site in sites" :key="site.url" :href="site.url" target="_blank" rel="noopener noreferrer"
                class="wp-card">
                <div class="wp-card-top">
                    <div class="browser-bar">
                        <span class="browser-dot"></span>
                        <span class="browser-dot"></span>
                        <span class="browser-dot"></span>
                        <span class="browser-url">{{ site.url.replace('https://www.', '') }}</span>
                    </div>
                    <div class="wp-preview">
                        <img :src="screenshotUrl(site.url)" :alt="site.name + ' screenshot'" class="wp-screenshot"
                            loading="lazy" />
                        <div class="wp-screenshot-overlay"></div>
                    </div>
                </div>
                <div class="wp-card-body">
                    <div class="wp-meta">
                        <span class="pill">WordPress</span>
                        <span class="pill">{{ site.tld }}</span>
                    </div>
                    <div class="wp-card-title">{{ site.name }}</div>
                    <div class="wp-link">
                        <svg viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path d="M2 10L10 2M10 2H5M10 2v5" stroke="currentColor" stroke-width="1.2"
                                stroke-linecap="round" stroke-linejoin="round" />
                        </svg>
                        Besøg site
                    </div>
                </div>
            </a>
        </div>
    </section>
</template>


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

    @media (max-width: 640px) {
        flex-direction: column;
        align-items: flex-start;
        gap: 0.75rem;
    }
}

.header-note {
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
    max-width: 260px;
    text-align: right;
    line-height: 1.6;
}

.wp-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.25rem;

    @media (max-width: 1024px) {
        grid-template-columns: repeat(2, 1fr);
    }

    @media (max-width: 540px) {
        grid-template-columns: 1fr;
    }
}

.wp-card {
    border: 1px solid rgba(255, 243, 198, 0.08);
    border-radius: var(--radius-lg);
    overflow: hidden;
    background: var(--dark2);
    transition: border-color 0.25s, transform 0.2s;
    display: flex;
    flex-direction: column;
    cursor: pointer;

    &:hover {
        border-color: rgba(215, 151, 6, 0.3);
        transform: translateY(-3px);

        .wp-screenshot-overlay {
            opacity: 0;
        }

        .wp-link {
            color: var(--gold);
        }
    }
}

.wp-card-top {
    display: flex;
    flex-direction: column;
}

.browser-bar {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.6rem 0.85rem;
    background: rgba(9, 48, 40, 0.8);
    border-bottom: 1px solid rgba(255, 243, 198, 0.05);
    flex-shrink: 0;
}

.browser-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: rgba(255, 243, 198, 0.15);
    flex-shrink: 0;

    &:nth-child(1) {
        background: rgba(255, 96, 92, 0.5);
    }

    &:nth-child(2) {
        background: rgba(255, 189, 46, 0.5);
    }

    &:nth-child(3) {
        background: rgba(40, 201, 64, 0.5);
    }
}

.browser-url {
    font-family: var(--mono);
    font-size: 0.65rem;
    color: var(--text-muted);
    letter-spacing: 0.03em;
    margin-left: 0.3rem;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    opacity: 0.7;
}

.wp-preview {
    height: 160px;
    position: relative;
    overflow: hidden;
    background: var(--dark3);
}

.wp-screenshot {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: top;
    display: block;
}

.wp-screenshot-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, transparent 50%, rgba(13, 63, 53, 0.4) 100%);
    transition: opacity 0.3s;
}

.wp-card-body {
    padding: 1rem 1.25rem 1.25rem;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
    flex: 1;
}

.wp-meta {
    display: flex;
    gap: 0.4rem;
}

.wp-card-title {
    font-family: var(--serif);
    font-size: 1.1rem;
    color: var(--cream);
    line-height: 1.2;
}

.wp-link {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--text-muted);
    letter-spacing: 0.06em;
    display: flex;
    align-items: center;
    gap: 0.35rem;
    margin-top: auto;
    transition: color 0.2s;

    svg {
        width: 11px;
        height: 11px;
    }
}
</style>
