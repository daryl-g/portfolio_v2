<script lang="ts">
	// Flowbite components
	import { Alert } from 'flowbite-svelte';

	// Lists
	let greetings: [string, string, string] = ['Hi', 'Hallo', 'Xin chào'];
</script>

<main class="home-container">
	<div class="hero">
		<div class="intro">
			<div class="greetings">
				<p>Hi, Hallo, Xin chào!</p>
			</div>
			<div class="name">
				<p>I'm</p>
				<p>Daryl Dao</p>
			</div>
			<div class="description"></div>
		</div>
		<div class="small-showcase"></div>
	</div>
</main>

<style>
	.hero {
		width: 100%;
	}
</style>
