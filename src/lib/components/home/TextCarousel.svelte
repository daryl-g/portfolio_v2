<script lang="ts">
	// Lists
	const greetings: [string, string, string] = ['Hi!', 'Hallo!', 'Xin chào!'];
</script>

<div class="carousel" aria-label="Greetings carousel">
	<div class="greeting-track" aria-hidden="true">
		{#each [...greetings, greetings[0]] as greeting}
			<p>{greeting}</p>
		{/each}
	</div>
</div>

<style>
	/* Greetings carousel */
	.carousel {
		height: 6em;
		overflow: hidden;
	}

	.greeting-track p {
		margin: 0;
		line-height: 1.2em;
		animation: greeting-carousel 9s infinite;
		font-family: 'Tilt Neon', sans-serif;
		color: #bb9af7;
		font-weight: 500;
	}

	/* Carousel animation */
	@keyframes greeting-carousel {
		0%,
		20% {
			transform: translateY(0);
		}
		25%,
		45% {
			transform: translateY(-1.2em);
		}
		50%,
		70% {
			transform: translateY(-2.4em);
		}
		75%,
		100% {
			transform: translateY(-3.6em);
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.greeting-track p {
			animation: none;
		}
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		.greeting-track p {
			height: 1.2em;
			font-size: 5em;
		}
	}
</style>
