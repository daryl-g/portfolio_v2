<script lang="ts">
	// Custom components
	import Hero from '$lib/components/home/Hero.svelte';
	import HobbiesGrid from '$lib/components/home/HobbiesGrid.svelte';
	import Divider from '$lib/components/Divider.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<div class="home-container">
	<Hero />
	<Divider thickness={'1px'} />
	<div class="hobbies-section">
		<div class="section-title">
			<p>More things I made!</p>
		</div>
		<HobbiesGrid />
	</div>
	<Footer />
</div>

<style>
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

	/* Sections styling */
	.hobbies-section {
		width: 90vw;
		margin-inline: auto;
	}
</style>
