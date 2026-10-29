<script lang="ts">
	// Take option to display social links
	let { displayLinks = true }: { displayLinks?: boolean } = $props();
	let isLinks: string = $derived(displayLinks ? 'flex' : 'none');

	// Custom component
	import Divider from './Divider.svelte';

	// Lists of links
	import links from '../data/footer_socials.json';
</script>

<footer class="footer">
	<Divider thickness={'1px'} />
	<div class="footer-content">
		<div class="credits">
			<div class="main-credits">
				<p>© 2026 - Daryl Dao</p>
			</div>
			<div class="sub-credits">
				<p>Made with ❤️ and a lot of electronic music. Like...a lot.</p>
			</div>
		</div>
		<div class="links" style={`display: ${isLinks}`}>
			{#each links as link}
				<a
					href={link.link}
					aria-label={link.label}
					target="_blank"
					rel="noopener"
					referrerpolicy="no-referrer-when-downgrade"
				>
					<i class="fa-{link.pack} fa-{link.icon}"></i>
				</a>
			{/each}
		</div>
	</div>
</footer>

<style>
	.footer-content {
		margin: 2rem 0;
		display: flex;
		justify-content: space-between;
	}

	.sub-credits {
		margin-top: 0.3rem;
	}

	.credits p {
		font-family: 'Source Serif 4', sans-serif;
	}

	.main-credits p {
		color: #ff4499;
		font-size: 1.2rem;
	}

	.sub-credits p {
		color: #8bbdda;
		font-size: 0.8rem;
	}

	.links {
		display: flex;
		gap: 0.8rem;
	}

	.links a {
		color: #23b8d2;
		font-size: 1.5rem;
	}
</style>
