<script lang="ts">
	// Custom components
	import TextCarousel from '$lib/components/home/TextCarousel.svelte';
	import ShowcaseCarousel from '$lib/components/home/ShowcaseCarousel.svelte';
	import Divider from '$lib/components/Divider.svelte';
	import OccupationsList from '$lib/components/home/OccupationsList.svelte';
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
		<div class="small-showcase">
			<ShowcaseCarousel />
		</div>
	</div>
	<Divider />
	<OccupationsList />
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

		/* Showcase carousel */
		.small-showcase {
			width: 55%;
			margin-top: 4rem;
			margin-bottom: 4rem;
		}
	}
	@media (max-width: 767px) {
		/* Showcase carousel */
		.small-showcase {
			margin-bottom: 3rem;
		}
	}
</style>
