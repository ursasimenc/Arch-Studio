<script>
	import Carousel from "$lib/components/Carousel/Carousel.svelte";
	import welcomeImg from "$lib/assets/home/desktop/image-welcome.jpg";
	import ProjectCard from "$lib/components/ProjectCard/ProjectCard.svelte";
</script>

<svelte:head>
	<title>Arch Studio</title>
</svelte:head>

<main>
	<Carousel />
	<section id="welcome">
		<div>
			<div class="h1">
				<h1>Welcome</h1>
			</div>
			<h2>Welcome to Arch Studio</h2>
			<div>
				<p>
					We have a unique network and skillset to help bring your projects to life. Our small team of highly skilled individuals combined with our large network put us in a strong position to deliver
					exceptional results.
				</p>
				<p>Over the past 10 years, we have worked on all kinds of projects. From stations to high-rise buildings, we create spaces that inspire and delight.</p>
				<p></p>
				<p>
					We work closely with our clients so that we understand the intricacies of each project. This allows us to work in harmony the surrounding area to create truly stunning projects that will
					stand the test of time.
				</p>
			</div>
		</div>
		<img id="welcome-img" src="{welcomeImg}" alt="A building" />
	</section>
	<section id="team">
		<div>
			<div>
				<h2>Small team, big ideas</h2>
			</div>
			<a class="button" href="/about_us">
				About Us
				<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="white" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg>
			</a>
		</div>
	</section>
	<section id="featured">
		<div class="header">
			<h2>Featured</h2>
			<a href="/portfolio" class="button"
				>See All
				<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="white" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg></a
			>
		</div>
		<div class="projects">
			<ProjectCard classes="del-sol" title="Project Del Sol" desc="View All Projects" number="1" />
			<ProjectCard classes="twotwoeight" title="228B Tower" desc="View All Projects" number="2" />
			<ProjectCard classes="prototype" title="Le Prototype" desc="View All Projects" number="3" />
		</div>
		<a href="/portfolio" class="button" id="mobile-projects"
			>See All
			<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="white" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg></a
		>
	</section>
</main>

<style>
	main {
		width: 100%;
		max-width: var(--maxWidth);

		@media (max-width: 1050px) {
			max-width: var(--maxWidthTablet);
		}
	}

	section#welcome {
		display: flex;
		align-items: center;
		justify-content: end;
		gap: 7.8rem;
		width: 100%;
		position: relative;

		@media (max-width: 573px) {
			padding: 0 2rem;
		}

		& div {
			width: 446px;
			position: relative;

			@media (max-width: 1050px) {
				width: 100%;
			}

			& .h1 {
				position: relative;
				z-index: -1;

				& h1 {
					position: absolute;
					color: var(--veryLightGrey);
					z-index: -1;
					top: -19rem;
					left: -12rem;

					@media (max-width: 1050px) {
						left: 0rem;
						top: -17rem;
					}

					@media (max-width: 573px) {
						visibility: hidden;
					}
				}

				@media (max-width: 573px) {
					height: 2px;
					width: 65px;
					background-color: var(--veryLightGrey);
					top: -4rem;
				}
			}
		}

		& h2 {
			position: relative;

			@media (max-width: 1050px) {
				margin: 0;
			}
		}

		& #welcome-img {
			z-index: -2;
			@media (max-width: 1050px) {
				display: none;
			}
		}
	}

	section#team {
		width: 100%;
		height: 560px;
		background-color: rgb(52, 101, 173);
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		background-image: url("$lib/assets/home/desktop/image-small-team.jpg");
		position: relative;

		& > div {
			width: 100%;
			height: 100%;
			background-color: rgba(0, 0, 0, 0.425);
			padding: 11rem;
			display: flex;
			flex-direction: column;
			gap: 1.25rem;

			& div {
				max-width: 445px;
				color: white;

				& h2 {
					margin: 0;
				}
			}

			@media (max-width: 1050px) {
				justify-content: center;
				padding: 3rem;
			}
		}

		@media (max-width: 573px) {
			width: 100vw;
		}
	}

	section#featured {
		display: flex;
		flex-direction: column;
		gap: 3.5rem;
		width: 100%;
		max-width: var(--maxWidth);

		@media (max-width: 576px) {
			padding-inline: 2rem;
		}

		& .header {
			display: flex;
			justify-content: space-between;
			align-items: center;
			gap: 1.5rem;

			& h2 {
				margin: 0;
			}

			& .button {
				@media (max-width: 576px) {
					display: none;
				}
			}
		}

		& .projects {
			widows: 100%;
			display: flex;
			justify-content: space-between;

			@media (max-width: 1050px) {
				flex-direction: column;
				justify-content: flex-start;
				align-items: flex-start;
				gap: 2rem;
			}
		}

		& #mobile-projects {
			width: 100%;
			display: flex;
			justify-content: center;

			@media (min-width: 567px) {
				display: none;
			}
		}
	}
</style>
