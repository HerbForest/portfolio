<template>
    <footer>
        <span class="footer-note">© 2026 Valdemar · Web Developer</span>
        <span class="footer-note footer-status">
            <span class="status-dot"></span>
            Åben for praktik
        </span>
    </footer>
</template>

<style scoped>
footer {
    border-top: 1px solid rgba(255, 243, 198, 0.06);
    padding: 2rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1100px;
    margin: 0 auto;

    @media (max-width: 1024px) {
        padding: 2rem 2.5rem;
    }

    @media (max-width: 640px) {
        padding: 1.5rem;
        flex-direction: column;
        gap: 0.75rem;
        text-align: center;
    }
}

.footer-note {
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 0.05em;
}

.footer-status {
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.status-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--gold);
    opacity: 0.8;
}
</style>
