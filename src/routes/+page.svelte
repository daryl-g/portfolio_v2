<script lang="ts">
	// Lists
	const greetings: [string, string, string] = ['Hi!', 'Hallo!', 'Xin chào!'];
</script>

<main class="home-container">
	<div class="hero">
		<div class="intro">
			<div class="greetings">
				<span class="material-symbols-outlined"> waving_hand </span>
				<div class="carousel" aria-label="Greetings carousel">
					<div class="greeting-track" aria-hidden="true">
						{#each [...greetings, greetings[0]] as greeting}
							<p>{greeting}</p>
						{/each}
					</div>
				</div>
			</div>
			<div class="description">
				<p>I enjoy solving problems and questions.</p>
				<p>I enjoy building solutions and engineering data.</p>
			</div>
		</div>
		<div class="small-showcase"></div>
	</div>
</main>

<style>
	.hero {
		width: 100%;
		display: flex;
	}

	.intro {
		width: 50%;
		margin-top: 6rem;
		margin-bottom: 6rem;
	}

	.greetings {
		display: flex;
	}

	.greetings > span {
		font-size: 5rem;
		color: #bb9af7;
		margin-right: 1.2rem;
	}

	/* Greetings carousel */
	.carousel {
		height: 6em;
		overflow: hidden;
	}

	.greeting-track p {
		height: 1.2em;
		margin: 0;
		line-height: 1.2em;
		animation: greeting-carousel 9s infinite;
		font-family: 'Tilt Neon', sans-serif;
		color: #bb9af7;
		font-weight: 500;
		font-size: 5em;
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

	/* Description */
	.description {
		font-family: 'Source Serif 4', sans-serif;
		color: #ff4499;
		font-size: 1.5rem;
		font-weight: 500;
		margin-top: 1rem;
	}

	/* Showcase carousel */
	.small-showcase {
		width: 50%;
		margin-top: 6rem;
		margin-bottom: 6rem;
	}
</style>
