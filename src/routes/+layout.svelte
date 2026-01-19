<script lang="ts">
    import '../app.css';
    import favicon from '$lib/assets/favicon.ico';
	import { fade } from 'svelte/transition';

    // Lägg till $state() här för att Svelte ska lyssna på ändringar
    let isMenuOpen = $state(false);

    function closeMenu() {
        isMenuOpen = false;
    }

    const navLinks = [
        { href: '#about', label: 'Om mig' },
        { href: '#projects', label: 'Portfolio' },
        { href: '#skills', label: 'Kompetenser' },
        { href: '#contact', label: 'Kontakt' }
    ];
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&display=swap" rel="stylesheet">
</svelte:head>

<header class="sticky top-0 z-50 bg-paper/90 backdrop-blur-md px-6 py-4 border-b border-ink/10">
    <div class="max-w-6xl mx-auto flex justify-between items-center">
        
        <a href="/" class="group" on:click={closeMenu}>
            <h1 class="font-heading text-ink text-2xl md:text-3xl tracking-tight">
                Theres <span class="font-light">Söder</span>
            </h1>
            <p class="text-[10px] uppercase tracking-[0.2em] text-ink/60 -mt-1 hidden sm:block">
                Pedagog & Utvecklare
            </p>
        </a>

        <nav class="hidden md:flex space-x-8 items-center" aria-label="Huvudnavigering">
            {#each navLinks as link}
                <a href="/{link.href}" class="text-sm font-bold text-ink hover:text-accent transition-colors relative group">
                    {link.label}
                    <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-accent transition-all group-hover:w-full"></span>
                </a>
            {/each}
        </nav>

        <div class="md:hidden">
            <button 
                class="text-ink p-2 focus:outline-none" 
                on:click={() => isMenuOpen = !isMenuOpen}
                aria-expanded={isMenuOpen}
                aria-label="Meny"
            >
                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 transition-transform duration-300 {isMenuOpen ? 'rotate-90' : ''}" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    {#if isMenuOpen}
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                    {:else}
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
                    {/if}
                </svg>
            </button>
        </div>
    </div>

    {#if isMenuOpen}
        <div 
            transition:fade={{ duration: 200 }}
            class="md:hidden absolute top-full left-0 w-full bg-paper border-b border-ink/10 shadow-xl py-8 px-6 space-y-6 flex flex-col items-center z-50"
        >
            {#each navLinks as link}
                <a 
                    href="/{link.href}" 
                    class="text-2xl font-bold text-ink hover:text-accent transition-colors"
                    on:click={closeMenu}
                >
                    {link.label}
                </a>
            {/each}
        </div>
    {/if}
</header>
<main>
    <slot />
</main>
<footer class="bg-paper border-t border-ink/10">
    <section id="contact" class="max-w-6xl mx-auto py-24 px-6 text-center">
        <span class="text-accent font-bold uppercase tracking-widest text-sm mb-4 block">Hör av dig</span>
        <h2 class="text-4xl md:text-5xl font-extrabold text-ink mb-6">Låt oss skapa något tillsammans</h2>
        <p class="text-lg mb-12 max-w-xl mx-auto leading-relaxed">
            Oavsett om det gäller ett nytt projekt, en pedagogisk utmaning eller om du bara vill byta tankar kring kod och lärande – tveka inte att sträcka ut en hand.
        </p>
        
        <div class="flex flex-col sm:flex-row items-center justify-center gap-6 md:gap-12">
            <a href="mailto:uktsoder@gmail.com" 
                class="group flex items-center space-x-2 text-xl font-bold text-ink hover:text-accent transition-colors">
                <span class="bg-ink text-paper p-2 rounded-lg group-hover:bg-accent transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                    </svg>
                </span>
                <span>Maila mig</span>
            </a>

            <a href="https://linkedin.com/in/theres-söder-828092137" target="_blank" rel="noopener noreferrer"
                class="group flex items-center space-x-2 text-xl font-bold text-ink hover:text-accent transition-colors">
                <span class="bg-ink text-paper p-2 rounded-lg group-hover:bg-accent transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                    </svg>
                </span>
                <span>LinkedIn</span>
            </a>

            <a href="https://github.com/theressoder" target="_blank" rel="noopener noreferrer"
                class="group flex items-center space-x-2 text-xl font-bold text-ink hover:text-accent transition-colors">
                <span class="bg-ink text-paper p-2 rounded-lg group-hover:bg-accent transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                    </svg>
                </span>
                <span>GitHub</span>
            </a>
        </div>
    </section>

    <div class="bg-ink py-8 px-6 text-paper/60 text-sm">
        <div class="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-4">
            <p>© 2026 Theres Söder | Analyserande görare i Edsbyn</p>
            <div class="flex space-x-6">
                <a href="#about" class="hover:text-paper transition-colors">Tillbaka till toppen ↑</a>
            </div>
        </div>
    </div>
</footer>
