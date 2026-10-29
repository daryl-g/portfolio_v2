<div class="contact-message">
	<div class="chat">
		<div class="avatar">
			<img
				src="https://cdn.discordapp.com/avatars/397320027767963649/34f92173ebb4520c7ec6276af4b48acb.webp?size=80"
				alt="Max-Verstappen-answering-a-question"
			/>
		</div>
		<div class="contents">
			<div class="header">
				<h3>Daryl</h3>
			</div>
			<ul class="messages">
				<li>
					<p>
						Hi there! I might not be here often, but you can find me in other corners of the
						internet.
					</p>
				</li>
				<li><p>But please reach out nonetheless!</p></li>
			</ul>
		</div>
	</div>
	<div class="message">
		<div class="typing-indicator">
			{#each { length: 3 }}
				<div class="typing-dot">
					<span class="material-symbols-outlined">circle</span>
				</div>
			{/each}
			<p>User is typing</p>
		</div>
		<div class="message-box">
			<div class="attach-button">
				<span class="material-symbols-outlined">add</span>
			</div>
			<p>Message Daryl</p>
			<div class="send-button">
				<span class="material-symbols-outlined">send</span>
			</div>
		</div>
	</div>
</div>

<style>
	/* Message box styling */
	.contact-message {
		display: flex;
		flex-direction: column;
		min-height: 2.75rem;
		padding: 1rem;
		margin-top: 1.0625rem;
		background: linear-gradient(45deg, #19153c, #04010a);
		border-radius: inherit;
		word-wrap: break-word;
	}

	.chat {
		display: flex;
		user-select: text;
	}

	.avatar {
		height: 40px;
		aspect-ratio: 1 / 1;
		inset-inline-start: 16px;
		margin-top: 0.125rem;
		margin-right: 0.8rem;
	}

	.avatar img {
		border-radius: 50%;
	}

	.contents {
		color: #dbdee1;
		display: flex;
		flex-direction: column;
	}

	.header h3 {
		display: inline;
		position: relative;
		vertical-align: baseline;
		font-size: 1rem;
		font-weight: 500;
		line-height: 1.375rem;
	}

	.messages {
		display: flex;
		flex-direction: column;
		gap: 0.3rem;
	}

	.messages p {
		color: #b5bac1;
		line-height: 1.375rem;
		word-wrap: break-word;
	}

	/* Typing indicator styling */
	.material-symbols-outlined {
		font-variation-settings: 'FILL' 1;
	}

	.typing-indicator {
		color: #d8d8f7;
		display: flex;
		flex-direction: row;
		margin-top: 1rem;
	}

	.typing-indicator p {
		height: 10%;
		margin: 0.4rem 0 0 0.4rem;
		font-size: 0.7rem;
		opacity: 0.75;
	}

	/* Typing animation */
	.typing-dot span {
		display: inline-block;
		font-size: 0.5rem;
		opacity: 0.75;
		animation: typing-bounce 1.2s ease-in-out infinite;
	}

	.typing-dot:nth-child(1) span {
		animation-delay: 0s;
	}

	.typing-dot:nth-child(2) span {
		animation-delay: 0.15s;
	}

	.typing-dot:nth-child(3) span {
		animation-delay: 0.3s;
	}

	@keyframes typing-bounce {
		0%,
		60%,
		100% {
			transform: translateY(0);
			opacity: 0.5;
		}
		30% {
			transform: translateY(-4px);
			opacity: 1;
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.typing-dot span {
			animation: none;
		}
	}

	/* Message box styling */
	.message-box {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		text-align: start;
		margin-top: 0.3rem;
		padding: 0.5rem;
		background-color: #1a163f;
		border-radius: 10px;
		user-select: text;
	}

	.message-box span {
		width: 20px;
		height: 20px;
	}

	.message-box p {
		color: #d8d8f7;
		font-weight: 200;
		opacity: 0.3;
		margin-top: 0.6rem;
		line-height: 1.375rem;
	}

	.attach-button {
		color: #abacb2;
		border-radius: 20%;
		padding: 0.5rem 0.6rem 0.2rem 0.2rem;
		cursor: pointer;
	}

	.send-button {
		color: white;
		background-color: #5865f2;
		border-radius: 20%;
		padding: 0.5rem 0.6rem 0.2rem 0.5rem;
		cursor: pointer;
	}
</style>
