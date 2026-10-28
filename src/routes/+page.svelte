<script lang="ts">
	// Custom components
	import TextCarousel from '$lib/components/home/TextCarousel.svelte';
	import ShowcaseGrid from '$lib/components/home/ShowcaseGrid.svelte';
	import Divider from '$lib/components/Divider.svelte';
</script>

<main class="home-container">
	<div class="hero">
		<div class="intro">
			<div class="greetings">
				<span class="material-symbols-outlined"> waving_hand </span>
				<TextCarousel />
			</div>
			<div class="description">
				<p>I enjoy solving problems and questions.</p>
				<p>I enjoy building solutions and engineering data.</p>
			</div>
		</div>
	</div>
	<Divider />
	<ShowcaseGrid />
	<Divider />
</main>

<style>
	.hero {
		width: 100%;
	}

	.intro {
		margin-top: 4rem;
		margin-bottom: 4rem;
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
		}

		.intro {
			width: 45%;
		}
	}
</style>
