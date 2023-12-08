<script>
	import aboutImg from "$lib/assets/about/desktop/image-hero.jpg";
	import heritageImg from "$lib/assets/about/desktop/image-heritage.jpg";
	import Leader from "$lib/components/Leader/Leader.svelte";
</script>

<svelte:head>
	<title>About Us</title>
</svelte:head>

<main>
	<section id="about">
		<img src="{aboutImg}" alt="A person making designs using a laptop" width="635px" height="720px" />
		<div>
			<h1>About</h1>
			<div class="line"></div>
			<h2>Your team of professionals</h2>
			<p>
				Our small team of world-class professionals will work with you every step of the way. Strong relationships are at the core of everything we do. This extends to the relationship our projects
				have with their surroundings.
			</p>
		</div>
	</section>
	<section id="heritage">
		<div>
			<div class="line"></div>
			<h2>Our Heritage</h2>
			<div class="content">
				<p>
					Founded in 2007, we started as a trio of architects. Our complimentary skills and relentless attention to detail turned Arch into one of the most sought after boutique firms in the country.
				</p>
				<p>
					Speciliazing in Urban Design allowed us to focus on creating exceptional structures that live in harmony with their surroundings. We consider every detail from every surrounding element to
					inform our designs.
				</p>
				<p>Our small team of world-class professionals provides input on every project.</p>
			</div>
		</div>
		<img src="{heritageImg}" alt="A building" width="540px" height="568px" />
	</section>
	<section id="leaders">
		<h2>The Leaders</h2>
		<div class="leaders">
			<Leader teamMember="{0}" />
			<Leader teamMember="{1}" />
			<Leader teamMember="{2}" />
			<Leader teamMember="{3}" />
		</div>
	</section>
</main>

<style>
	section#about {
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
				top: -16.5rem;
				left: -12rem;

				@media (max-width: 1050px) {
					top: -11.5rem;
					left: 5rem;
				}

				@media (max-width: 576px) {
					display: none;
				}
			}
		}

		& > img {
			filter: brightness(0.65);

			@media (max-width: 1050px) {
				src: url("../../lib/assets/about/tablet/image-hero.jpg");
				position: absolute;
				height: 720px;
				width: 100%;
				object-fit: cover;
			}

			@media (max-width: 576px) {
				src: url("../../lib/assets/about/mobile/image-hero.jpg");
				width: 100vw;
				max-height: 240px;
				object-fit: cover;
				position: relative;
			}
		}
	}

	section#heritage {
		width: 100%;
		height: 568px;
		max-width: var(--maxWidth);
		display: flex;
		justify-content: space-between;
		align-items: flex-end;

		@media (max-width: 576px) {
			padding-inline: 2rem;
		}

		& > div {
			width: 446px;
			height: 100%;
			position: relative;
			display: flex;
			flex-direction: column;
			justify-content: space-between;

			@media (max-width: 1050px) {
				width: 100%;
			}

			& .line {
				width: 65px;
				height: 1px;
				background-color: var(--lightGrey);
			}

			& .content {
				display: flex;
				flex-direction: column;
				gap: 2rem;
			}

			& h2,
			p {
				margin: 0;
			}

			& h2 {
				width: 50%;
			}
		}
		& > img {
			filter: brightness(0.95);

			@media (max-width: 1050px) {
				display: none;
			}
		}
	}

	section#leaders {
		width: 100%;
		display: flex;
		justify-content: space-between;
		max-width: var(--maxWidth);

		@media (max-width: 576px) {
			padding-inline: 2rem;
		}

		@media (max-width: 1050px) {
			flex-direction: column;
			align-items: flex-start;
		}

		& h2 {
			width: 250px;

			@media (max-width: 576px) {
				width: 150px;
			}
		}

		& .leaders {
			display: grid;
			grid-template-columns: repeat(2, 1fr);
			gap: 1.5rem;

			@media (max-width: 1050px) {
				grid-template-columns: repeat(2, 245px);
			}

			@media (max-width: 576px) {
				grid-template-columns: repeat(1, 100%);
			}
		}
	}
</style>
