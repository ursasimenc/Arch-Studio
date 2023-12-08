<script lang="ts">
	import contactImg from "$lib/assets/contact/desktop/image-hero.jpg";

	let nameInvalid = false;
	let emailInvalid = false;
	let messageInvalid = false;
	let showMessage = false;
	$: emailMessage = "Can't be empty";

	function checkForm(e: any) {
		e.preventDefault();
		emailMessage = "Can't be empty";

		const name = e.target[0].value;
		const email = e.target[1].value;
		const message = e.target[2].value;

		name === "" ? (nameInvalid = true) : (nameInvalid = false);
		message === "" ? (messageInvalid = true) : (messageInvalid = false);
		email === "" ? (emailInvalid = true) : (emailInvalid = false);

		if (email.includes("@") && email.includes(".")) {
			emailInvalid = false;
		} else {
			emailMessage = "Please use a valid email address";
			emailInvalid = true;
		}

		console.log(e.target);

		if (!nameInvalid && !emailInvalid && !messageInvalid) {
			showMessage = true;
		}
	}
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

<main>
	<section id="contact">
		<img src="{contactImg}" alt="A telephone" width="635px" height="720px" />
		<div>
			<h1>Contact</h1>
			<div class="line"></div>
			<h2>Tell us about your project</h2>
			<p>
				We’d love to hear more about your project. Please, leave a message below or give us a call. We have two offices, one in Texas and one in Tennessee. If you find yourself nearby, come say hello!
			</p>
		</div>
	</section>
	<section id="details">
		<div class="heading">
			<div class="line"></div>
			<h2>Contact Details</h2>
		</div>
		<div class="content">
			<div class="location">
				<h5>Main Office</h5>
				<div>
					<div>
						<p>Mail: archone@mail.com</p>
						<p>Address : 1892 Chenoweth Drive TN</p>
						<p>Phone : 123-456-3451</p>
					</div>
					<button class="link">
						View on Map
						<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="var(--darkBlue)" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg
						>
					</button>
				</div>
			</div>

			<div class="location">
				<h5>Office II</h5>
				<div>
					<div>
						<p>Mail: archtwo@mail.com</p>
						<p>Address: 3399 Wines Lane TX</p>
						<p>Phone: 832-123-4321</p>
					</div>
					<button class="link">
						View on Map
						<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="var(--darkBlue)" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg
						>
					</button>
				</div>
			</div>
		</div>
	</section>
	<section id="map"></section>
	<section id="form">
		<h2>Connect with us</h2>
		<form class="content" novalidate on:submit="{(e) => checkForm(e)}">
			<label for="name" aria-label="Name">
				<input class="{nameInvalid ? 'invalid' : ''}" type="text" name="Name" id="name" placeholder="Name" />
				<div class="error">Can't be empty</div></label
			>
			<label for="email" aria-label="Email">
				<input class="{emailInvalid ? 'invalid' : ''}" type="email" name="email" id="email" placeholder="Email" />
				<div class="error" id="email-error">{emailMessage}</div></label
			>
			<label for="message" aria-label="Message">
				<textarea class="{messageInvalid ? 'invalid' : ''}" name="message" id="message" placeholder="Message" cols="30" rows="6"></textarea>
				<div class="error">Can't be empty</div></label
			>
			<div class="{showMessage ? 'message' : 'no-message'}">
				{#if showMessage}
					<div class="message">Your message has been sent!</div>
				{/if}

				<button type="submit">
					<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="white" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg></button
				>
			</div>
		</form>
	</section>
</main>

<style>
	section#contact {
		width: 100%;
		height: 720px;
		max-width: var(--maxWidth);
		display: flex;
		justify-content: flex-start;
		align-items: flex-end;
		position: relative;

		@media (max-width: 1050px) {
			max-width: var(--maxWidthTablet);
			justify-content: flex-end;
			align-items: flex-end;
		}

		@media (max-width: 576px) {
			max-width: var(--maxWidthTablet);
			justify-content: start;
			align-items: start;
			flex-direction: column;
			height: 100%;
		}

		& > div {
			width: 446px;
			position: relative;
			display: flex;
			flex-direction: column;
			gap: 3rem;
			box-shadow: -90px -89px 0 90px white;
			background-color: white;

			@media (max-width: 1050px) {
				box-shadow: 10px -49px 0 50px white;
			}

			@media (max-width: 576px) {
				box-shadow: -70px -39px 0px 0px white;
				padding-inline: 2rem;
				gap: 1.5rem;
				width: 100vw;
			}

			& .line {
				width: 65px;
				height: 1px;
				background-color: var(--lightGrey);

				@media (max-width: 576px) {
					display: none;
				}
			}

			& h1,
			h2,
			p {
				margin: 0;

				@media (max-width: 576px) {
					margin: 0 1rem;
				}
			}

			& h1 {
				position: absolute;
				color: var(--veryLightGrey);
				top: -17.5rem;
				left: -24.5rem;

				@media (max-width: 1050px) {
					top: -11.5rem;
					left: -1.5rem;
				}

				@media (max-width: 576px) {
					display: none;
				}
			}
		}

		& > img {
			filter: brightness(0.8) saturate(1.75);

			@media (max-width: 1050px) {
				src: url("../../lib/assets/contact/tablet/image-hero.jpg");
				position: absolute;
				height: 720px;
				width: 100%;
				object-fit: cover;
			}

			@media (max-width: 576px) {
				src: url("../../lib/assets/contact/mobile/image-hero.jpg");
				width: 100vw;
				max-height: 240px;
				object-fit: cover;
				position: relative;
			}
		}
	}

	section#details {
		width: 100%;
		max-width: var(--maxWidth);
		display: grid;
		grid-template-columns: 1fr 2fr;
		gap: 3rem;
		height: 300px;

		@media (max-width: 1050px) {
			max-width: var(--maxWidthTablet);
			height: 100%;
			grid-template-columns: 1fr;
		}

		@media (max-width: 576px) {
			padding-inline: 2rem;
		}

		& > .heading {
			display: flex;
			justify-content: flex-start;
			align-items: flex-start;
			flex-direction: column;
			gap: 4rem;
			height: 100%;
		}

		& .line {
			width: 65px;
			height: 1px;
			background-color: var(--lightGrey);
		}

		& .content {
			display: flex;
			gap: 4rem;
			height: 100%;
			padding-top: 4rem;

			@media (max-width: 1050px) {
				flex-direction: column;
			}

			& > div {
				display: flex;
				flex-direction: column;
				gap: 1rem;

				& > div {
					display: flex;
					flex-direction: column;
					gap: 2rem;

					@media (max-width: 1050px) and (min-width: 576px) {
						flex-direction: row;
						justify-content: space-between;
					}

					& > button {
						padding: 0;
						padding-block: 1rem;
					}
				}
			}
		}

		& h2,
		h5,
		p {
			margin: 0;
		}

		& h2 {
			width: 50%;
			line-height: 62px;

			@media (max-width: 576px) {
				line-height: 48px;
			}
		}
	}
	& > img {
		filter: brightness(0.95);

		@media (max-width: 1050px) {
			display: none;
		}
	}

	section#map {
		width: 100%;
		height: 560px;
		max-width: var(--maxWidth);
		display: flex;
		justify-content: flex-start;
		align-items: flex-end;
		position: relative;
		background-image: url("../../lib/assets/contact/desktop/image-map.png");

		@media (max-width: 1050px) and (min-width: 576px) {
			max-width: var(--maxWidthTablet);
			aspect-ratio: 1;
			background-image: url("../../lib//assets//contact/tablet/image-map.png");
			background-position: center;
			background-size: cover;
			background-repeat: no-repeat;
			height: auto;
		}

		@media (max-width: 576px) {
			height: auto;
			width: 100vw;
			aspect-ratio: 1;
			max-width: none;
			background-image: url("../../lib//assets//contact/mobile/image-map.png");
			background-position: center;
			background-size: cover;
			background-repeat: no-repeat;
		}
	}

	section#form {
		width: 100%;
		max-width: var(--maxWidth);
		display: grid;
		grid-template-columns: 1fr 2fr;
		gap: 3rem;
		height: fit-content;

		@media (max-width: 1050px) {
			max-width: var(--maxWidthTablet);
			height: 100%;
			grid-template-columns: 1fr;
		}

		@media (max-width: 576px) {
			padding-inline: 2rem;
			gap: 1rem;
		}

		& > h2 {
			margin: 0;

			@media (max-width: 576px) {
				width: 160px;
			}
		}

		& > form {
			display: flex;
			flex-direction: column;
			gap: 1rem;

			& input,
			textarea {
				width: 100%;
				padding: 1rem;
				border: none;
				font: inherit;
				box-shadow: 0px 2px 0px -1px var(--darkBlue);

				resize: none;
				font-weight: 700;

				&::placeholder {
					color: var(--lightGrey);
				}

				&:focus {
					outline: none;
					box-shadow: 0px 4px 0px -1px var(--darkBlue);
				}

				&.invalid {
					box-shadow: 0px 2px 0px -1px var(--red);
					margin-bottom: 0;
				}
			}

			& input {
				margin-bottom: 3px;
			}

			& label {
				position: relative;

				& .error {
					position: absolute;
					right: 1rem;
					bottom: 1rem;
					color: var(--red);
					text-align: right;
					font-weight: 700;
					letter-spacing: -0.01756rem;
					display: none;
				}
			}

			& .invalid {
				& + .error {
					display: block;
				}
			}

			& > div {
				width: 100%;
				display: flex;

				& > .message {
					font-weight: 700;
				}

				& > button {
					padding: 0;
					width: 5rem;
					aspect-ratio: 1;
					display: flex;
					justify-content: center;
					align-items: center;
					position: relative;
					top: -1.25rem;
				}

				&.no-message {
					justify-content: flex-end;
				}

				&.message {
					justify-content: space-between;
				}
			}
		}
	}
</style>
