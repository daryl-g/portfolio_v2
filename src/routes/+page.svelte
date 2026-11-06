<script lang="ts">
	// Custom components
	import Hero from '$lib/components/home/Hero.svelte';
	import Blog from '$lib/components/home/Blog.svelte';
	import ShowcaseGrid from '$lib/components/home/ShowcaseGrid.svelte';
</script>

<div class="home-container">
	<div class="hero-section">
		<Hero />
	</div>
	<div class="blog">
		<Blog />
	</div>
	<div class="projects-showcase">
		<ShowcaseGrid />
	</div>
</div>

<style>
	.home-container {
		display: grid;
		width: 95%;
		height: 90vh;
		max-height: 90vh;
		margin-inline: auto;
		margin-top: 3.5rem;
	}

	.hero-section,
	.blog,
	.projects-showcase {
		background-color: #0e101580;
		border-radius: 20px;
		overflow-y: hidden;
	}

	/* Responsive */
	@media (min-width: 768px) {
		.home-container {
			grid-template-rows: repeat(2, auto);
			grid-template-columns: 1.5fr 1fr;
			gap: 2rem 3rem;
		}
		.blog {
			grid-column: 2;
			grid-row: 1 / span 2;
		}
	}
	@media (max-width: 767px) {
		.home-container {
			grid-template-rows: repeat(3, auto);
			grid-template-columns: auto;
			gap: 1rem;
		}
		.blog {
			grid-row: 3;
		}
	}
</style>
