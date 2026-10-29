<script lang="ts">
	// Custom components
	import Footer from '$lib/components/Footer.svelte';
</script>

<div class="contact-content">
	<div class="contact-grid"></div>
	<Footer />
</div>

<style>
	.contact-content {
		height: 100vh;
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		.contact-content {
			width: 80vw;
			margin-inline: auto;
		}
	}
</style>
