<script lang="ts">
	// Default imports
	import './layout.css';
	import favicon from '$lib/assets/favicon.jpg';

	// Custom component imports
	import Header from '$lib/components/Header.svelte';

	// Transitions
	import { fly } from 'svelte/transition';
	import { page } from '$app/state';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<main class="portfolio">
	<Header />

	{#key page.url.pathname || page.url.href}
		<div
			class="page-transition"
			in:fly={{ x: 32, duration: 300 }}
			out:fly={{ x: -32, duration: 180 }}
		>
			{@render children()}
		</div>
	{/key}
</main>

<style>
	/* Global layout styling */
	:global(html, body) {
		height: 100vh;
		background: linear-gradient(45deg, #0a0022 0%, #1a163a 70%);
		background-size: 200% 100%;
		font-family: 'Noto Sans', 'Open Sans', sans-serif;
		margin: 0;
		padding: 0;
	}

	.portfolio {
		height: 99vh;
		max-height: 99vh;
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
