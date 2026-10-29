<script lang="ts">
	// Custom components
	import Footer from '$lib/components/Footer.svelte';
</script>

<div class="experience-content">
	<div class="experience-timeline"></div>
	<Footer />
</div>

<style>
	.experience-content {
		height: 100vh;
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		.experience-content {
			width: 80vw;
			margin-inline: auto;
		}
	}
</style>
