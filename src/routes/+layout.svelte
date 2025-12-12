<script lang="ts">
	// Default imports
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	// Custom components imports
	import AnimatedBg from '$lib/components/AnimatedBg.svelte';
	import Nav from '$lib/components/Nav.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<AnimatedBg />

<div class="app">
	<Nav />

	<main class="content-container">
		{@render children()}
	</main>
</div>

<style>
	/* Global layout styling */
	:global(html, body) {
		margin: 0;
		padding: 0;
		overflow: hidden; /* Hide scrolling */
	}

	.app {
		width: 100vw;
		height: 100vh;
		position: relative;
	}

	.content-container {
		width: 100%; /* Use the full width for the container, then adjust the content individually */
		height: 100%;
		margin: 0 auto; /* Center horizontally */
		position: relative;
		z-index: 1; /* Ensure content is above background */
	}
</style>
