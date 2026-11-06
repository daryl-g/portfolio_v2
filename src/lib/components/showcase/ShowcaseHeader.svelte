<script lang="ts">
	// Prop variables
	let {
		icon,
		title,
		colour
	}: {
		icon: string;
		title: string;
		colour: string;
	} = $props();
</script>

<div class="showcase-header" style:--gradient-colour={colour}>
	<span class="material-symbols-outlined">{icon}</span>
	<h1>{title}</h1>
</div>

<style>
	.showcase-header {
		display: flex;
		justify-content: center;
		align-items: center;
		min-height: 0;
		margin-top: 3rem;
		padding-block: 0.75rem 1.5rem;
		color: #fff;
		font-size: clamp(2rem, 4vw, 4rem);
		background: linear-gradient(180deg, rgba(10, 0, 43, 0) 75%, var(--gradient-colour) 130%);
		border-radius: 0 0 50% 50% / 0 0 40% 40%;
	}

	.showcase-header span {
		font-weight: 500;
		font-size: inherit;
		margin-right: 0.5rem;
	}

	.showcase-header h1 {
		font-family: 'Roboto Slab', sans-serif;
		font-weight: 600;
		line-height: 1.1;
	}
</style>
