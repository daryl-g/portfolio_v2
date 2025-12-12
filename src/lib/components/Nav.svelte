<!-- TypeScript logic for the navigation component -->
<script lang="ts">
	// Check open state of the nav borgor
	let isOpen = false;

	function toggleMenu() {
		isOpen = !isOpen;
	}

	// Routes
	const pages = [
		{ label: 'Home', href: '/' },
		{ label: 'Experience', href: '/experience' },
		{ label: 'Projects', href: '/projects' },
		{ label: 'Contact', href: '/contact' }
	];
</script>

<!-- HTML rendering of the component -->
<nav class="default-nav">
	<ul>
		{#each pages as page}
			<li>
				<a href={page.href}>{page.label}</a>
			</li>
		{/each}
	</ul>
</nav>

<nav class="nav-borgor">
	<button class="borgor-button" aria-label="Toggle navigation" on:click={toggleMenu}>
		<span class:open={isOpen}></span>
		<span class:open={isOpen}></span>
		<span class:open={isOpen}></span>
	</button>

	{#if isOpen}
		<div class="menu-overlay">
			<button class="close-overlay" aria-label="Close nav overlay" on:click={toggleMenu}>
				<span class:open={isOpen}> </span>
			</button>
			<ul>
				{#each pages as page}
					<li>
						<a href={page.href} on:click={toggleMenu}>{page.label}</a>
					</li>
				{/each}
			</ul>
		</div>
	{/if}
</nav>

<!-- Styling for the navigation component -->
<style>
	/* Desktop nav */
	.default-nav {
		display: none;
		position: fixed;
		top: 2rem;
		left: 7.5%;
		z-index: 1000;
	}

	.default-nav ul {
		display: flex;
		gap: 2rem;
		list-style: none;
		margin: 0;
		padding: 0;
	}

	.default-nav a {
		color: white;
		text-decoration: none;
		font-size: 1rem;
		font-weight: 500;
		transition: color 0.3s ease;
		position: relative;
	}

	/* When each nav component is hovered on */
	.default-nav a:hover {
		color: #00d9ff;
	}

	/* Highlight the page after the page is clicked */
	.default-nav a::after {
		content: '';
		position: absolute;
		bottom: -4px;
		left: 0;
		width: 0;
		height: 2px;
		background: #00d9ff;
		transition: width 0.3s ease;
	}

	.default-nav a:hover::after {
		width: 100%;
	}

	/* Mobile/Responsive nav */
	.nav-borgor {
		display: block;
		position: fixed;
		top: 2rem;
		right: 2rem;
		z-index: 1000; /* Basically just put it above any kind of content */
	}

	.nav-borgor ul {
		list-style: none;
		padding: 0;
		margin: 0;
		text-align: center;
	}

	.nav-borgor li {
		margin: 2rem 0;
	}

	.nav-borgor a {
		color: white;
		text-decoration: none;
		font-size: 2rem;
		font-weight: 500;
		transition: color 0.3s ease;
	}

	.nav-borgor a:hover {
		color: #00d9ff;
	}

	.borgor-button {
		background: transparent;
		border: none;
		cursor: pointer;
		display: flex;
		flex-direction: column;
		gap: 0.4rem;
		padding: 0.5rem;
	}

	.borgor-button span {
		width: 2rem;
		height: 0.2rem;
		background: white;
		transition: all 0.3 ease;
	}

	.borgor-button span.open:nth-child(1) {
		transform: rotate(45deg) translate(0.5rem, 0.5rem);
	}

	.borgor-button span.open:nth-child(2) {
		opacity: 0;
	}

	.borgor-button span.open:nth-child(3) {
		transform: rotate(-45deg) translate(0.5rem, -0.5rem);
	}

	/* Overlay menu for the burger nav */
	.menu-overlay {
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		background: rgba(0, 0, 0, 0.95);
		display: flex;
		justify-content: center;
		align-items: center;
	}

	/* Close button for the overlay */
	.close-overlay {
		position: absolute;
		top: 2rem;
		right: 2rem;
		background: transparent;
		border: none;
		cursor: pointer;
	}

	/* Responsive query */
	@media (min-width: 768px) {
		.default-nav {
			display: block;
		}

		.nav-borgor {
			display: none;
		}
	}
</style>
