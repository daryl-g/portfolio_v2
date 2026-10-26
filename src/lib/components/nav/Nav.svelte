<script lang="ts">
	import { page } from '$app/state';

	// Custom component
	import NavBorgor from './NavBorgor.svelte';

	// Routes
	const pages = $state([
		{ label: 'Work', href: '/work' },
		{ label: 'Showcase', href: '/showcase' },
		{ label: 'Contact', href: '/contact' },
		{ label: 'Archive', href: '/archive' }
	]);
</script>

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

<NavBorgor />

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

	/* Responsive */
	@media (min-width: 768px) {
		.default-nav {
			display: flex;
		}
	}
	@media (max-width: 767px) {
		.default-nav {
			display: none;
		}
	}
</style>
