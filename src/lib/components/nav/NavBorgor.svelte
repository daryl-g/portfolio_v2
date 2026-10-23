<script lang="ts">
	// Check open state of the nav borgor
	let isOpen = false;

	function toggleMenu() {
		isOpen = !isOpen;
	}
</script>

<nav class="nav-borgor">
	<button class="borgor-button" aria-label="Toggle navigation" on:click={toggleMenu}>
		<span class="material-symbols-outlined"> menu </span>
	</button>
</nav>

<style>
	/* Mobile/Responsive nav */
	.nav-borgor {
		display: block;
		position: fixed;
		top: 2rem;
		right: 2rem;
	}

	.borgor-button {
		border: none;
		cursor: pointer;
	}

	.borgor-button span {
		color: white;
		font-size: 2rem;
	}

	/* Responsive */
	@media (min-width: 768px) {
		.nav-borgor {
			display: none;
		}
	}
</style>
