<template>
    <section id="kontakt">
        <div class="contact-inner">
            <div class="section-label" style="justify-content: center;">Kontakt</div>
            <h2 class="contact-big">Lad os <em>snakke</em></h2>
            <p class="body-text" style="margin-bottom: 2rem; color: var(--text-muted);">
                Jeg søger en praktikplads indenfor frontend-udvikling fra begyndelsen af august. 2026.
                Jeg er fleksibel på lokation og åben for både remote og på kontoret.
            </p>
            <a href="mailto:fe13valseh@gmail.com" class="contact-email">fe13valseh@gmail.com</a>

            <div class="contact-links">
                <a href="https://github.com/HerbForest" target="_blank" rel="noopener noreferrer" class="contact-link">
                    <svg viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                        <path
                            d="M7 1C3.69 1 1 3.69 1 7c0 2.65 1.72 4.9 4.1 5.7.3.06.41-.13.41-.29v-.96c-1.67.36-2.02-.8-2.02-.8-.27-.7-.66-.88-.66-.88-.54-.37.04-.36.04-.36.6.04.91.61.91.61.53.9 1.38.64 1.72.49.05-.38.21-.64.38-.79-1.31-.15-2.69-.65-2.69-2.91 0-.64.23-1.17.61-1.58-.06-.15-.26-.75.06-1.57 0 0 .5-.16 1.63.61A5.67 5.67 0 017 4.68c.5.002 1.01.068 1.49.2 1.13-.77 1.63-.61 1.63-.61.32.82.12 1.42.06 1.57.38.41.61.94.61 1.58 0 2.27-1.39 2.77-2.71 2.91.21.19.4.55.4 1.11v1.65c0 .16.11.35.41.29C11.29 11.9 13 9.65 13 7c0-3.31-2.69-6-6-6z"
                            fill="currentColor" />
                    </svg>
                    GitHub
                </a>

                <a href="https://www.linkedin.com/in/valdemar-sehested-37bba324b/" target="_blank"
                    rel="noopener noreferrer" class="contact-link">
                    <svg viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                        <rect x="1" y="1" width="12" height="12" rx="2" fill="currentColor" opacity="0.15"
                            stroke="currentColor" stroke-width="0.8" />
                        <rect x="2.5" y="5" width="2" height="6.5" fill="currentColor" />
                        <circle cx="3.5" cy="3.5" r="1" fill="currentColor" />
                        <path
                            d="M6.5 5v6.5h2V8c0-.8.6-1.5 1.5-1.5s1.5.7 1.5 1.5v3.5h2V7.8C13.5 6 12.3 5 10.8 5c-.9 0-1.7.4-2.3 1V5H6.5z"
                            fill="currentColor" />
                    </svg>
                    LinkedIn
                </a>

                <a href="/umbraco_professional_certification.pdf" target="_blank" rel="noopener noreferrer"
                    class="contact-link">
                    <svg viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                        <path d="M3 1.5A1.5 1.5 0 014.5 0H9l4 4v8.5A1.5 1.5 0 0111.5 14h-7A1.5 1.5 0 013 12.5v-11z"
                            stroke="currentColor" stroke-width="1.1" stroke-linecap="round" />
                        <path d="M9 0v4h4" stroke="currentColor" stroke-width="1.1" stroke-linecap="round" />
                        <path d="M5 8h4M5 10.5h2.5" stroke="currentColor" stroke-width="1.1" stroke-linecap="round" />
                    </svg>
                    Umbraco Certifikat
                </a>
            </div>
        </div>
    </section>
</template>

<style scoped>
section {
    max-width: 1100px;
    margin: 0 auto;
    padding: 6rem 4rem;
}

.contact-inner {
    text-align: center;
    max-width: 600px;
    margin: 0 auto;
}

.contact-big {
    font-family: var(--serif);
    font-size: clamp(2.5rem, 6vw, 4.5rem);
    line-height: 1.05;
    color: var(--cream);
    margin-bottom: 1.5rem;

    em {
        font-style: italic;
        color: var(--gold);
    }
}

.contact-email {
    font-family: var(--mono);
    font-size: 1rem;
    color: var(--gold);
    border-bottom: 1px solid rgba(215, 151, 6, 0.4);
    padding-bottom: 2px;
    transition: color 0.2s, border-color 0.2s;

    &:hover {
        color: var(--gold-light);
        border-color: var(--gold-light);
    }
}

.contact-links {
    display: flex;
    justify-content: center;
    gap: 2rem;
    margin-top: 2.5rem;
    flex-wrap: wrap;

    @media (max-width: 400px) {
        gap: 1.25rem;
    }
}

.contact-link {
    font-family: var(--mono);
    font-size: 0.8rem;
    color: var(--text-muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: color 0.2s;

    &:hover {
        color: var(--cream);
    }

    svg {
        width: 14px;
        height: 14px;
    }
}
</style>
