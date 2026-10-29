<script lang="ts">
	// Custom components
	import Footer from '$lib/components/Footer.svelte';
	import Discord from '$lib/components/contact/Discord.svelte';
</script>

<div class="contact-content">
	<div class="contact-grid">
		<Discord />
		<div class="contact-email">
			<a
				href="mailto:Daryl Dao<daohoang.thai@gmail.com>?subject=Connect with you!"
				target="_blank"
				rel="noopener noreferrer"
				referrerpolicy="no-referrer-when-downgrade"
			>
				<button type="button">
					<p>Let's chat!</p>
					<span class="material-symbols-outlined">arrow_outward</span>
				</button>
			</a>
		</div>
		<div class="contact-bluesky">
			<a
				href="https://bsky.app/profile/daryldao.com"
				target="_blank"
				rel="noopener noreferrer"
				referrerpolicy="no-referrer-when-downgrade"
			>
				<button type="button">
					<p>DM me!</p>
					<span class="material-symbols-outlined">arrow_outward</span>
				</button>
			</a>
		</div>
		<div class="contact-socials">
			<div class="linkedin"></div>
			<div class="github"></div>
		</div>
	</div>
	<Footer displayLinks={false} />
</div>

<style>
	.contact-content {
		min-height: 98vh;
		display: flex;
		flex-direction: column;
	}

	.contact-grid,
	.contact-socials {
		display: grid;
		grid-template-rows: repeat(2, auto);
		grid-template-columns: repeat(2, 1fr);
		border-radius: 20px;
	}

	.contact-grid {
		flex: 1;
		gap: 1rem;
		align-content: center;
		margin-inline: auto;
	}

	.contact-email,
	.contact-bluesky {
		border-radius: inherit;
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		.contact-content {
			width: 80vw;
			margin-inline: auto;
		}
		.contact-grid {
			width: 50vw;
		}
	}
	@media (max-width: 767px) {
		.contact-grid {
			width: 90%;
		}
	}
</style>
