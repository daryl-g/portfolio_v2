<script lang="ts">
	// This showcase grid is a merger between the ShowcaseCarousel and OccupationsList components
	// after I realised they can be a single component while still serving multiple purposes.

	// Lists of showcase images and properties
	import images from '../../data/home_showcase.json';
	import design_images from '../../data/design_images.json';

	// Custom component
	import Slideshow from '../Slideshow.svelte';
</script>

<div class="showcase-grid">
	{#each images.slice(0, 3) as work}
		<div class="{work.tag}-showcase-component">
			<a href="/showcase/{work.tag}">
				<div class="{work.tag}-showcase-overlay">
					<span class="material-symbols-outlined" style="color:{work.colour}">{work.icon}</span>
					<p style="color:{work.colour}">{work.title}</p>
				</div>
				<img src={work.src} alt={work.alt} />
			</a>
		</div>
	{/each}
	<div class="graphic-design-showcase-component">
		<a href="/showcase/graphic-design">
			<div class="graphic-design-showcase-overlay">
				<span class="material-symbols-outlined" style="color:{images[3].colour}"
					>{images[3].icon}</span
				>
				<p style="color:{images[3].colour}">{images[3].title}</p>
			</div>
			<Slideshow
				images={design_images['images']}
				ariaLabel={'Vizzes and graphics slideshow'}
				interval={5000}
			/>
		</a>
	</div>
</div>

<style>
	.showcase-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		grid-template-rows: repeat(2, 49%);
		gap: 1rem;
		padding: 1rem;
		width: 100%;
		height: 100%;
	}

	/* Title overlay */
	.showcase-grid > div {
		position: relative;
		border-radius: 20px;
	}

	.showcase-grid > div > a {
		border-radius: inherit;
	}

	.showcase-grid > div > a > div {
		position: absolute;
		inset: 0;
		z-index: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		border-radius: inherit;
	}

	.showcase-grid img {
		display: block;
		width: 100%;
		height: 100%;
		object-fit: cover;
		object-position: center;
		border-radius: inherit;
	}

	.showcase-grid span {
		font-size: 5rem;
	}

	.showcase-grid p {
		font-family: 'Source Serif 4', sans-serif;
		font-size: 2rem;
		font-weight: 500;
	}

	/* Only displays on hover */
	.showcase-grid > div:hover > a > div,
	.showcase-grid > div:focus-within > a > div {
		opacity: 1;
		visibility: visible;
		transition:
			opacity 180ms ease,
			visibility 0s;
	}

	/* Background gradient for individual overlays */
	.football-analysis-showcase-overlay {
		background: linear-gradient(180deg, #0a002bcc 80%, #ff4499 110%);
	}

	.football-analysis-showcase-overlay:hover {
		background: linear-gradient(180deg, #0a002bcc 60%, #ff4499 110%);
	}

	.data-science-showcase-overlay {
		background: linear-gradient(180deg, #0a002bcc 80%, #ea7600 110%);
	}

	.data-science-showcase-overlay:hover {
		background: linear-gradient(180deg, #0a002bcc 60%, #ea7600 110%);
	}

	.software-dev-showcase-overlay {
		background: linear-gradient(180deg, #0a002bcc 80%, #13dbb7 110%);
	}

	.software-dev-showcase-overlay:hover {
		background: linear-gradient(180deg, #0a002bcc 60%, #13dbb7 110%);
	}

	.graphic-design-showcase-overlay {
		background: linear-gradient(180deg, #0a002bcc 80%, #05e0fc 110%);
	}

	.graphic-design-showcase-overlay:hover {
		background: linear-gradient(180deg, #0a002bcc 60%, #05e0fc 110%);
	}
</style>
