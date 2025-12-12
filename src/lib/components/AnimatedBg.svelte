<div class="animated-bg"></div>

<style>
	.animated-bg {
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		z-index: 0; /* Always stay as the background */
		background: linear-gradient(45deg, #1a1a2e, #16213e, #0f3460);
		background-size: 400% 400%;
		animation: gradient 15s ease infinite; /* Fun animation part */
	}

	/* Change position of the gradient animation */
	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}
</style>
