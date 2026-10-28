<script lang="ts">
	// Default imports
	import './layout.css';
	import favicon from '$lib/assets/favicon.jpg';

	// Custom component imports
	import Header from '$lib/components/Header.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="portfolio">
	<Header />

	<main class="content-container">
		{@render children()}
	</main>
</div>

<style>
	/* Global layout styling */
	:global(html, body) {
		background: linear-gradient(180deg, #0a0022, #231050);
		background-size: 400% 200%;
		margin: 0;
		padding: 0;
	}

	.portfolio {
		height: 100vh;
		position: relative;
		margin-inline: auto;
	}

	.content-container {
		width: 100%;
		height: 100%;
		margin-top: 2.5rem;
		position: relative;
		z-index: 1;
	}

	/* Responsive portfolio width */
	@media (min-width: 768px) {
		.portfolio {
			width: 70vw;
		}
	}
	@media (max-width: 767px) {
		.portfolio {
			width: 90vw;
		}
	}
</style>
