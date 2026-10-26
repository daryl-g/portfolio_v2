<script lang="ts">
	// List of clients
	const clients: {
		logo: string;
		name: string;
		alt: string;
	}[] = $state([
		{ logo: '', name: 'Brisbane Olympic FC', alt: 'Brisbane Olympic FC logo' },
		{ logo: '', name: 'Melbourne Knights FC', alt: 'Melbourne Knights FC logo' },
		{ logo: '', name: 'Brisbane Roar FC', alt: 'Brisbane Roar FC logo' },
		{ logo: '', name: 'Football Australia', alt: 'Football Australia logo' },
		{ logo: '', name: 'Stenhousemuir FC', alt: 'Stenhousemuir FC logo' },
		{ logo: '', name: 'Kashy Australia', alt: 'Kashy Australia logo' },
		{ logo: '', name: 'Entain ANZ', alt: 'Entain Australia & New Zealand logo' },
		{ logo: '', name: 'Ronnie Dog Media', alt: 'Ronnie Dog Media logo' },
		{ logo: '', name: 'Between the Posts', alt: 'Between the Posts logo' },
		{ logo: '', name: 'Read Southampton', alt: 'Read Southampton logo' }
	]);
</script>

<div class="clients">
	<div class="clients-title">
		<p>Teams and companies I've worked with</p>
		<ul class="clients-list">
			{#each clients as item}
				<li>
					<div class="client-logo">
						<img src={item.logo} class="img-logo" alt={item.alt} />
					</div>
					<p>{item.name}</p>
				</li>
			{/each}
		</ul>
	</div>
</div>

<style></style>
