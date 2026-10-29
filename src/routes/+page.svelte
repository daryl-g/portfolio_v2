<script lang="ts">
	// Custom components
	import TextCarousel from '$lib/components/home/TextCarousel.svelte';
	import ShowcaseGrid from '$lib/components/home/ShowcaseGrid.svelte';
	import HobbiesGrid from '$lib/components/home/HobbiesGrid.svelte';
	import Divider from '$lib/components/Divider.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<div class="home-container">
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
	<Divider thickness={'1px'} />
	<div class="section-title">
		<p>Contributions</p>
	</div>
	<ShowcaseGrid />
	<Divider thickness={'1px'} />
	<div class="section-title">
		<p>Hobbies</p>
	</div>
	<HobbiesGrid />
	<Footer />
</div>

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

	/* Section title */
	.section-title {
		width: fit-content;
		margin: 1rem 0;
		padding: 0.3rem 0.7rem;
		user-select: none;
		background-color: #90ee90;
		border-radius: 20px;
	}

	.section-title p {
		color: #1a1b26;
		font-family: 'Source Code Pro', sans-serif;
		font-weight: 500;
		font-size: 1.2rem;
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		.home-container {
			width: 80vw;
			margin-inline: auto;
		}
		.hero {
			display: flex;
		}
	}
</style>
