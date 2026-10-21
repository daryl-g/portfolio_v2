<div class="animated-bg"></div>

<style>
	.animated-bg {
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		z-index: 0; /* Always stay as the background */
		background: linear-gradient(180deg, #0a0022, #231050, #1e438e);
		background-size: 400% 300%;
		animation: gradient 50s ease infinite;
	}

	/* Change position of the gradient animation */
	@keyframes gradient {
		0% {
			background-position: 100% 100%;
		}
		50% {
			background-position: 100% 0%;
		}
		100% {
			background-position: 100% 100%;
		}
	}
</style>
