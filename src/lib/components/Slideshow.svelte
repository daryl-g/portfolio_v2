<script lang="ts">
	// Take list of images, custom aria labels, image aspect ratios, and interval between images
	let {
		images,
		ariaLabel = 'Photo slideshow',
		aspectRatio = '1 / 1',
		interval = 10000
	}: {
		images: { link: string; alt: string }[];
		ariaLabel?: string;
		aspectRatio?: string;
		interval?: number;
	} = $props();

	// Calculate interval between images for the slideshow
	import { onMount } from 'svelte';

	let currentIndex = $state(0);

	onMount(() => {
		if (images.length < 2) return;

		// Time interval between images
		const intervalId: number = window.setInterval(() => {
			currentIndex = (currentIndex + 1) % images.length;
		}, interval);

		return () => window.clearInterval(intervalId);
	});
</script>

<div class="image-slideshow" aria-label={ariaLabel} style:--aspect-ratio={aspectRatio}>
	{#each images as image, index}
		<img
			class:active={index === currentIndex}
			src={image.link}
			alt={image.alt}
			aria-hidden={index !== currentIndex}
		/>
	{/each}
</div>

<style>
	/* Photo slideshow styling */
	.image-slideshow {
		position: relative;
		overflow: hidden;
		aspect-ratio: var(--aspect-ratio);
		width: 100%;
		height: 100%;
	}

	.image-slideshow img {
		position: absolute;
		inset: 0;
		width: 100%;
		height: 100%;
		object-fit: cover;
		object-position: center;
		opacity: 0;
		border-radius: 20px;
		transition: opacity 700ms ease;
	}

	.image-slideshow img.active {
		opacity: 1;
	}

	@media (prefers-reduced-motion: reduce) {
		.image-slideshow img {
			transition: none;
		}
	}
</style>
