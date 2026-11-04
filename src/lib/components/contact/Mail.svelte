<div class="contact-email">
	<div class="new-email">
		<div class="header">
			<h3>Let's connect!</h3>
		</div>
		<div class="email-content">
			<div class="sender">
				<p>Daryl Dao (daohoang.thai@gmail.com)</p>
				<hr />
			</div>
			<div class="subject">
				<p>Let's connect!</p>
				<hr />
			</div>
			<div class="typing-indicator">
				<span></span>
			</div>
		</div>
	</div>
	<a
		class="mail-button"
		href="mailto:Daryl Dao<daohoang.thai@gmail.com>?subject=Let's connect!"
		target="_blank"
		rel="noopener noreferrer"
		referrerpolicy="no-referrer-when-downgrade"
	>
		<button type="button">
			<p>Email me</p>
			<span class="material-symbols-outlined">arrow_outward</span>
		</button>
	</a>
</div>

<style>
	.contact-email {
		display: flex;
		flex-direction: column;
		background-color: #d3d3d5;
		border-radius: inherit;
	}

	.contact-email h3,
	.contact-email p {
		font-family: 'Google Sans', sans-serif;
	}

	/* Mailbox styling */
	.new-email {
		padding: 1rem 1rem 0 1rem;
		border-radius: 20px;
	}

	.header {
		height: 3vh;
		background-color: #f0f4f9;
		border-top-left-radius: 10px;
		border-top-right-radius: 10px;
	}

	.header h3 {
		font-size: 0.9rem;
		font-weight: 500;
		padding: 0.3rem 0.8rem 0;
	}

	.email-content {
		height: 100%;
		background-color: #fff;
		font-size: 0.8rem;
		padding-bottom: 7%;
	}

	.sender,
	.subject {
		padding-left: 0.8rem;
		padding-right: 0.8rem;
	}

	.sender p,
	.subject p {
		padding-top: 0.5rem;
		padding-bottom: 0.5rem;
	}

	.sender hr,
	.subject hr {
		border-color: #eceff1;
		height: 0.5px;
	}

	/* Typing text cursor animation */
	.typing-indicator span {
		display: block;
		width: 1px;
		height: 1rem;
		margin: 0.6rem 0 0 0.8rem;
		background-color: #333;
		animation: cursor-blink 1s steps(2, start) infinite;
	}

	@keyframes cursor-blink {
		to {
			visibility: hidden;
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.typing-indicator span {
			animation: none;
		}
	}

	/* Button styling */
	.mail-button {
		background-color: #d3d3d5;
		margin-top: auto;
		padding-top: 0.5rem;
		border-bottom-left-radius: 20px;
		border-bottom-right-radius: 20px;
	}

	.mail-button button {
		display: flex;
		flex-direction: row;
		justify-content: center;
		width: 90%;
		margin-inline: auto;
		margin-bottom: 0.8rem;
		padding: 0.3rem 0;
		background-color: #1b61d1;
		color: #fff;
		border-radius: 20px;
		cursor: pointer;
	}

	.mail-button > button > span {
		font-size: 1.5rem;
		margin-left: 0.5rem;
	}
</style>
