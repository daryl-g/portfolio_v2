<script lang="ts">
	// List of blog articles
	import articles from '../../data/articles_list.json';
	// List of images
	import images from '../../data/imgs_slideshow.json';

	// Calculate interval between images for the slideshow
	import { onMount } from 'svelte';

	let currentIndex = $state(0);

	onMount(() => {
		if (images.length < 2) return;

		// Time interval between images (currently sets at 10s)
		const intervalId: number = window.setInterval(() => {
			currentIndex = (currentIndex + 1) % images.length;
		}, 10000);

		return () => window.clearInterval(intervalId);
	});
</script>

<div class="hobbies-grid">
	<div class="blog-component">
		<div class="blog-header">
			<a
				class="blog-homepage"
				href="https://www.talking-tactics.com"
				target="_blank"
				rel="noopener noreferrer"
				aria-label="Talking Tactics logo"
			>
				<img
					src="https://substackcdn.com/image/fetch/$s_!I5H7!,e_trim:10:white/e_trim:10:transparent/h_40,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6f01cb50-e81b-42e9-8953-26efabeb0a0f_1000x261.png"
					alt="Talking Tactics logo"
					style="max-height:20px;"
				/>
			</a>
			<a
				class="blog-subscribe"
				href="https://www.talking-tactics.com/subscribe?utm_source=menu&simple=true&next=https%3A%2F%2Fwww.talking-tactics.com%2F"
				aria-label="Blog subscribe button"
			>
				<button type="button">Subscribe</button>
			</a>
		</div>
		<div class="blog-content">
			{#each [articles[0]] as article}
				<a
					href={article.link}
					target="_blank"
					rel="noopener"
					referrerpolicy="no-referrer-when-downgrade"
					class="latest-article"
				>
					<div class="latest-img">
						<img src={article.title_img} alt={article.alt_img} />
					</div>
					<div class="latest-info">
						<div class="latest-title">
							<h1>{article.title}</h1>
						</div>
						<div class="latest-description">
							<p>{article.desc}</p>
						</div>
						<div class="latest-published-date">
							<p>{article.date}</p>
						</div>
					</div>
				</a>
			{/each}
			<div class="article-divider">
				<hr class="divider" />
			</div>
			{#each [articles[1], articles[2]] as article}
				<a href={article.link} class="articles">
					<div class="titles">
						<div class="title">
							<h1>{article.title}</h1>
						</div>
						<div class="description">
							<p>{article.desc}</p>
						</div>
						<div class="published-date">
							<p>{article.date}</p>
						</div>
					</div>
					<div class="title-img">
						<img src={article.title_img} alt={article.alt_img} width={150} height={150} />
					</div>
				</a>
				<div class="article-divider">
					<hr class="divider" />
				</div>
			{/each}
		</div>
	</div>
	<div class="imgs-component" aria-label="Photo slideshow">
		{#each images as image, index}
			<img
				class:active={index === currentIndex}
				src={image.link}
				alt={image.alt}
				aria-hidden={index !== currentIndex}
			/>
		{/each}
	</div>
</div>

<style>
	.hobbies-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		margin: 1rem 0;
		gap: 1rem;
	}

	/* Styling the blog component like the current interface on Substack */
	.blog-component {
		background-color: rgb(8, 8, 34);
		border-radius: 20px;
	}

	/* Header styling */
	.blog-header {
		background-color: #0a0047;
		display: flex;
		justify-content: space-between;
		padding: 0.5rem 0.8rem;
		border-top-left-radius: 20px;
		border-top-right-radius: 20px;
	}

	.blog-header > .blog-subscribe {
		background-color: #90ee90;
		color: #363737;
		font-size: 0.8rem;
		font-weight: 500;
		padding: 0.4rem;
		border-radius: 5px;
	}

	.blog-header button {
		cursor: pointer;
	}

	/* Divider styling */
	.article-divider {
		padding: 4px 0;
		flex-direction: row;
	}

	.divider {
		appearance: none;
		background: 0 0;
		border-top: 1px solid #212138;
		width: 100%;
		height: 0;
		margin: 0;
		padding: 0;
	}

	/* Contents styling */
	.blog-content {
		padding: 0 0.7rem;
	}

	.blog-content a {
		display: grid;
		grid-template-columns: 1fr 72px;
		padding: 0;
		color: #d6d6df;
	}

	/* General contents styling */
	.blog-content > a > div > img {
		width: 100%;
		height: 100%;
		max-height: inherit;
		object-fit: hidden;
	}

	.titles,
	.latest-info {
		gap: 4px;
	}

	.title h1,
	.latest-title h1 {
		font-family: 'Roboto Slab', sans-serif;
		font-weight: 700;
		line-height: calc(1em * 1.411764705882353);
	}

	.description p,
	.latest-description p {
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		line-clamp: 2;
		overflow: hidden;
		text-decoration: unset;
		font-size: 12px;
		line-height: 20px;
		margin: 0;
	}

	/* Latest article styling */
	.blog-content a.latest-article {
		display: flex;
		flex-direction: column;
		height: 100%;
	}

	.latest-info {
		padding-top: 16px;
	}

	.latest-title {
		font-size: 18px;
		line-height: calc(1em * 1.2666666666666666);
	}

	.latest-img {
		position: relative;
		aspect-ratio: 1.77778 / 1;
		width: 100%;
		overflow: hidden;
	}

	.latest-img img {
		aspect-ratio: 1.77778 / 1;
	}

	/* Other articles styling */
	.articles {
		margin-top: 0.5rem;
	}

	.title h1 {
		font-size: 14px;
	}

	.published-date,
	.latest-published-date {
		display: inline;
		text-transform: uppercase;
		text-decoration: unset;
		letter-spacing: 0.2px;
		color: #9c9ca7;
		font-weight: 500;
		font-size: 11px;
		line-height: 20px;
		margin: 0;
	}

	.title-img {
		aspect-ratio: 1 / 1;
		width: 72px;
		height: 72px;
		border-radius: 12px;
		overflow: hidden;
	}

	.blog-content > a > .title-img > img {
		aspect-ratio: 1 / 1;
	}

	/* Photo slideshow styling */
	.imgs-component {
		position: relative;
		overflow: hidden;
		aspect-ratio: 4 / 3;
		height: 100%;
		border-radius: 20px;
	}

	.imgs-component img {
		position: absolute;
		inset: 0;
		width: 100%;
		height: 100%;
		object-fit: cover;
		opacity: 0;
		transition: opacity 700ms ease;
	}

	.imgs-component img.active {
		opacity: 1;
	}

	@media (prefers-reduced-motion: reduce) {
		.imgs-component img {
			transition: none;
		}
	}
</style>
