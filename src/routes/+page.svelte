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
		<HobbiesGrid />
	</div>
	<Footer />
</div>

<style>
	/* Sections styling */
	.hobbies-section {
		width: 90vw;
		margin-inline: auto;
	}
</style>
