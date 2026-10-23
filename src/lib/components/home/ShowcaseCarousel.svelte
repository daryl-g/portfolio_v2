<script lang="ts">
	// Flowbite component
	import { Carousel } from 'flowbite-svelte';

	// Lists of images
	import images from '../../data/home_showcase.json';
</script>

<Carousel {images} duration={3000} aria-label="Projects showcase" />
