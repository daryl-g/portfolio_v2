<script lang="ts">
	// This showcase grid is a merger between the ShowcaseCarousel and OccupationsList components
	// after I realised they can be a single component while still serving multiple purposes.

	// Lists of showcase images and properties
	import images from '../../data/home_showcase.json';
</script>

<div class="showcase-grid">
	{#each images as work}
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
</div>

<style>
	.showcase-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		grid-template-rows: repeat(2, 1fr);
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

	/* Background gradient for individual overlays */
	.software-dev-showcase-overlay {
		background: linear-gradient(45deg, #0a002bcc 80%, #13dbb7 100%);
	}

	.football-analysis-showcase-overlay {
		background: linear-gradient(135deg, #0a002bcc 80%, #ff4499 100%);
	}

	.data-science-showcase-overlay {
		background: linear-gradient(225deg, #0a002bcc 80%, #ea7600 100%);
	}

	.graphic-design-showcase-overlay {
		background: linear-gradient(315deg, #0a002bcc 80%, #05e0fc 100%);
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
</style>
