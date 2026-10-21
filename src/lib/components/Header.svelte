<script lang="ts">
	// Custom components
	import Nav from '$lib/components/Nav.svelte';
</script>

<header class="header-content">
	<a href="/" class="title-link">
		<div class="title">
			<p>Daryl Dao</p>
		</div>
	</a>

	<Nav />
</header>

<style>
	.header-content {
		display: flex;
		position: relative;
		top: 1.5rem;
		z-index: 1;
	}

	.title {
		text-decoration: none;
		font-family: 'Source Serif 4', sans-serif;
		font-weight: 500;
		font-size: 1.5rem;
		color: #e0af68;
	}
</style>
