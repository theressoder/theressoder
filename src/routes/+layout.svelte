<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=Carter+One&family=Quicksand:wght@300..700&display=swap" rel="stylesheet">
</svelte:head>

<header class="bg-stone px-6 py-4 flex justify-between items-center border-b-2 border-slate">
	<a href="/"><h1 class="font-heading text-slate text-shadow-lg text-5xl">TS</h1></a>
	<nav class="space-x-6 font-bold">
		<a href="/#about" class="text-slate hover:text-clay">Om mig</a>
		<a href="/#projects" class="text-slate hover:text-clay">Projekt</a>
		<a href="/#contact" class="text-slate hover:text-clay">Kontakt</a>
	</nav>
</header>
<main>
	{@render children?.()}
</main>
<footer>
	<!-- CONTACT -->
	<section id="contact" class="bg-stone py-20 px-6 text-center border-t-2 border-slate md:px-20">
		<h2 class="mb-6">Kontakt</h2>
		<p class="text-slate mb-8">Vill du samarbeta eller veta mer? <br>Hör av dig!</p>
		<div class="flex flex-col items-center md:flex-row md:justify-center md:items-center md:space-x-10 space-y-4 md:space-y-0">
			<a href="mailto:uktsoder@gmail.com" 
				class="text-lg font-bold text-clay hover:underline">Mail</a>
			<a href="https://linkedin.com/in/theres-söder-828092137" 
				class="text-lg font-bold text-moss hover:underline">LinkedIn</a>
			<a href="https://github.com/theressoder" 
				class="text-lg font-bold text-slate hover:underline">GitHub</a>
		</div>
	</section>
</footer>
