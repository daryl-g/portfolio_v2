<script lang="ts">
	// Lists
	const work_list: {
		icon: string;
		title: string;
		colour: string;
	}[] = [
		{ icon: 'sports_soccer', title: 'Football Analyst', colour: '#ff4499' },
		{ icon: 'bar_chart', title: 'Data Engineer & Scientist', colour: '#ea7600' },
		{ icon: 'computer', title: 'Software & Web Developer', colour: '#13dbb7' },
		{ icon: 'image', title: 'Graphic Designer', colour: '#05e0fc' },
		{ icon: 'edit', title: 'Blogger', colour: '#c605fc' }
	];
</script>

<div class="occupation-list">
	<ul class="occupations">
		{#each work_list as item}
			<li>
				<span class="material-symbols-outlined" style="color:{item.colour}">{item.icon}</span>
				<p style="color:{item.colour}">{item.title}</p>
			</li>
		{/each}
	</ul>
</div>

<style>
	/* Occupation list */
	.occupations {
		justify-content: space-between;
		margin: 2em 0;
	}

	.occupations > li {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}

	.occupations > li > span {
		display: grid;
		place-items: center;
		width: 1.7em;
		height: 1.7em;
		font-size: 3em;
		box-sizing: border-box;
		background-color: #0a004780;
		border-radius: 50%;
	}

	.occupations > li > p {
		font-family: 'Source Serif 4', sans-serif;
		font-size: 1.2em;
		font-weight: 600;
	}

	/* Responsive layout */
	@media (min-width: 768px) {
		/* Occupation list */
		.occupations {
			display: flex;
		}

		.occupations > li > p {
			margin-top: 0.5rem;
		}
	}
	@media (max-width: 767px) {
	}
</style>
