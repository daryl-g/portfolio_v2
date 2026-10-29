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

<main class="portfolio">
	<Header />

	{@render children()}
</main>

<style>
	/* Global layout styling */
	:global(html, body) {
		min-height: 100vh;
		background: linear-gradient(45deg, #0a0022, #1a163a);
		background-size: 200% 100%;
		margin: 0;
		padding: 0;
	}

	.portfolio {
		width: 90vw;
		height: 100vh;
		min-height: 0;
		display: flex;
		flex-direction: column;
		position: relative;
		overflow-y: auto;
		margin-inline: auto;
	}

	/* Hide scrollbar */
	.portfolio::-webkit-scrollbar {
		width: 0px;
		background: transparent;
	}

	.portfolio {
		scrollbar-width: none;
		-ms-overflow-style: none;
	}
</style>
