<!-- TypeScript logic for the navigation component -->
<script lang="ts">
	import { page } from '$app/state';

	// Check open state of the nav borgor
	let isOpen = false;

	function toggleMenu() {
		isOpen = !isOpen;
	}

	// Routes
	const pages = [
		{ label: 'Work', href: '/work' },
		{ label: 'Showcase', href: '/showcase' },
		{ label: 'Contact', href: '/contact' },
		{ label: 'Archive', href: '/archive' }
	];
</script>

<!-- HTML rendering of the component -->
<nav class="default-nav">
	<ul>
		{#each pages as item}
			<li>
				<a
					href={item.href}
					class:active={page.url.pathname === item.href}
					aria-current={page.url.pathname === item.href ? 'page' : undefined}
				>
					{item.label}
				</a>
			</li>
		{/each}
	</ul>
</nav>

<!-- Styling for the navigation component -->
<style>
	/* Desktop nav */
	.default-nav {
		width: 50%;
		margin-left: auto;
		text-align: right;
		justify-content: flex-end;
	}

	.default-nav ul {
		display: flex;
		gap: 3.5rem;
		list-style: none;
	}

	.default-nav a {
		color: #23b8d2;
		text-decoration: none;
		font-family: 'Source Code Pro', sans-serif;
		font-size: 1.2rem;
		font-weight: 600;
		transition: color 0.3s ease;
		position: relative;
	}

	/* Nav button hovering */
	.default-nav a:hover {
		color: #ff4499;
	}

	/* Nav button active */
	.default-nav a.active {
		color: #e0af68;
	}

	/* Responsive query */
	@media (min-width: 768px) {
		.default-nav {
			display: flex;
		}
	}
</style>
