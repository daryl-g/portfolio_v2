<script lang="ts">
	// This Hero component is a merger between the previous, simple Intro section
	// and the ShowcaseGrid because the previous Hero section looks very simple imo

	// Custom component
	import TextCarousel from './TextCarousel.svelte';

	// Lists of showcase images and properties
	import images from '../../data/home_showcase.json';
</script>

<div class="hero">
	<div class="hero-content">
		<div class="images">
			{#each [images[0], images[1]] as work}
				<div class="{work.tag}-showcase-component">
					<a href="/showcase/{work.tag}">
						<img src={work.src} alt={work.alt} />
					</a>
				</div>
			{/each}
		</div>
		<div class="intro">
			<div class="greetings">
				<span class="material-symbols-outlined"> waving_hand </span>
				<TextCarousel />
			</div>
			<div class="description">
				<p>I like solving problems and questions.</p>
				<p>I enjoy building solutions and engineering data.</p>
			</div>
		</div>
		<div class="images">
			{#each [images[2], images[3]] as work}
				<div class="{work.tag}-showcase-component">
					<a href="/showcase/{work.tag}">
						<img src={work.src} alt={work.alt} />
					</a>
				</div>
			{/each}
		</div>
	</div>
</div>

<style>
	.hero {
		width: 100%;
		height: 80vh;
	}

	.hero-content {
		width: 80%;
		margin-inline: auto;
		margin-top: 8rem;
	}

	/* Images collage styling */
	.images {
		display: flex;
		flex-direction: row;
		width: 90%;
		margin-inline: auto;
		justify-content: space-between;
	}

	.images img {
		display: block;
		width: 100%;
		height: 200px;
		border-radius: 10px;
	}

	/* Background gradient for individual overlays */
	.software-dev-showcase-component,
	.football-analysis-showcase-component,
	.data-science-showcase-component,
	.graphic-design-showcase-component {
		position: relative;
		isolation: isolate;
	}

	.software-dev-showcase-component::before,
	.football-analysis-showcase-component::before,
	.data-science-showcase-component::before,
	.graphic-design-showcase-component::before {
		content: '';
		position: absolute;
		inset: -40px;
		z-index: -1;
		background-size: 400% 400%;
		border-radius: 50%;
		filter: blur(18px);
		pointer-events: none;
	}

	.software-dev-showcase-component,
	.data-science-showcase-component {
		rotate: 5deg;
	}

	.software-dev-showcase-component::before {
		background: radial-gradient(ellipse, #13dbb799 100%);
	}

	.football-analysis-showcase-component,
	.graphic-design-showcase-component {
		rotate: 355deg;
	}

	.football-analysis-showcase-component::before {
		background: radial-gradient(ellipse, #ff449999 100%);
	}

	.data-science-showcase-component::before {
		background: radial-gradient(ellipse, #ea760099 100%);
	}

	.graphic-design-showcase-component::before {
		background: radial-gradient(ellipse, #05e0fc99 100%);
	}

	/* Intro section styling */
	.intro {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.greetings {
		display: flex;
		user-select: none;
	}

	.greetings > span {
		font-size: 5rem;
		color: #bb9af7;
		margin-right: 1.2rem;
	}

	/* Description */
	.description {
		display: inherit;
		flex-direction: inherit;
		justify-content: inherit;
		align-items: inherit;
		font-family: 'Source Serif 4', sans-serif;
		color: #ff4499;
		font-size: 1.5rem;
		font-weight: 500;
		margin-top: 1rem;
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		.hero {
			display: flex;
			flex-direction: column;
		}
	}
</style>
