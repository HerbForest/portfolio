<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
</script>
<template>
    <nav :class="{ open: menuOpen }">
        <div class="nav-logo">V<span>.</span>Dev</div>

        <button class="nav-toggle" @click="menuOpen = !menuOpen" :aria-expanded="menuOpen" aria-label="Toggle menu">
            <span></span>
            <span></span>
            <span></span>
        </button>

        <ul class="nav-links">
            <li><a href="#about" @click="menuOpen = false">Om mig</a></li>
            <li><a href="#projekter" @click="menuOpen = false">Projekter</a></li>
            <li><a href="#wordpress" @click="menuOpen = false">WordPress</a></li>
            <li><a href="#kompetencer" @click="menuOpen = false">Kompetencer</a></li>
            <li><a href="#kontakt" @click="menuOpen = false">Kontakt</a></li>
        </ul>

        <div class="nav-dot" title="Available for internship"></div>
    </nav>
</template>


<style scoped>
nav {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.25rem 4rem;
    background: rgba(9, 48, 40, 0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(215, 151, 6, 0.15);
}

.nav-logo {
    font-family: var(--serif);
    font-size: 1.4rem;
    color: var(--cream);
    letter-spacing: 0.01em;
    z-index: 101;

    span {
        color: var(--gold);
    }
}

.nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
    font-size: 0.875rem;
    font-weight: 400;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--text-muted);

    a:hover {
        color: var(--cream);
        transition: color 0.2s;
    }
}

.nav-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--gold);
    box-shadow: 0 0 8px rgba(215, 151, 6, 0.6);
    animation: pulse-dot 2s ease-in-out infinite;
}

.nav-toggle {
    display: none;
    flex-direction: column;
    gap: 5px;
    background: none;
    border: none;
    cursor: pointer;
    padding: 4px;
    z-index: 101;

    span {
        display: block;
        width: 22px;
        height: 1.5px;
        background: var(--cream);
        border-radius: 2px;
        transition: transform 0.25s, opacity 0.25s;
        transform-origin: center;
    }
}

nav.open .nav-toggle span:nth-child(1) {
    transform: translateY(6.5px) rotate(45deg);
}

nav.open .nav-toggle span:nth-child(2) {
    opacity: 0;
}

nav.open .nav-toggle span:nth-child(3) {
    transform: translateY(-6.5px) rotate(-45deg);
}

@keyframes pulse-dot {

    0%,
    100% {
        opacity: 1;
        transform: scale(1);
    }

    50% {
        opacity: 0.6;
        transform: scale(0.85);
    }
}

@media (max-width: 768px) {
    nav {
        padding: 1.1rem 1.5rem;
        flex-wrap: wrap;
    }

    .nav-toggle {
        display: flex;
    }

    .nav-dot {
        display: none;
    }

    .nav-links {
        display: none;
        width: 100%;
        flex-direction: column;
        gap: 0;
        padding: 1rem 0 0.5rem;
        border-top: 1px solid rgba(215, 151, 6, 0.1);
        margin-top: 0.5rem;

        li a {
            display: block;
            padding: 0.75rem 0;
            font-size: 0.9rem;
            color: var(--text-muted);
            border-bottom: 1px solid rgba(255, 243, 198, 0.05);
        }
    }

    nav.open .nav-links {
        display: flex;
    }
}
</style>
