<script lang="ts">
	// This Hero component is a merger between the previous, simple Intro section
	// and the ShowcaseGrid because the previous Hero section looks very simple imo

	// Custom component
	import TextCarousel from './TextCarousel.svelte';

	// Lists of showcase images and properties
	import images from '../../data/home_showcase.json';
</script>

<div class="hero">
	<div class="greetings">
		<span class="material-symbols-outlined"> waving_hand </span>
		<TextCarousel />
	</div>
	<div class="description">
		<p>I like solving problems and questions.</p>
		<p>I enjoy building solutions and engineering data.</p>
	</div>
</div>

<style>
	.hero {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100%;
		padding: 1rem;
	}

	/* Intro section styling */

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
