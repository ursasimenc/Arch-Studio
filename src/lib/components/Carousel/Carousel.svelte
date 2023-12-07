<script>
	import { onMount } from "svelte";
	const projects = [
		{
			title: "Project Paramour",
			description: "Project made for an art museum near Southwest London. Project Paramour is a statement of bold, modern architecture.",
			class: "paramour",
		},
		{
			title: "Seraph Station",
			description:
				"The Seraph Station project challenged us to design a unique station that would transport people through time. The result is a fresh and futuristic model inspired by space stations.",
			class: "seraph",
		},
		{
			title: "Federal II Tower",
			description: "A sequel theme project for a tower originally built in the 1800s. We achieved this with a striking look of brutal minimalism with modern touches.",
			class: "federal",
		},
		{
			title: "Trinity Bank Tower",
			description: "Trinity Bank challenged us to make a concept for a 84 story building located in the middle of a city with a high earthquake frequency.",
			class: "trinity",
		},
	];

	let currentProject = 0;

	onMount(() => {
		setInterval(() => {
			if (currentProject == projects.length - 1) {
				currentProject = 0;
			} else {
				currentProject++;
			}
		}, 5000);
	});
</script>

<section class="{projects[currentProject].class}">
	<div class="wrapper">
		<div>
			<h2>{projects[currentProject].title}</h2>
			<p>{projects[currentProject].description}</p>
		</div>
		<a class="button" href="/portfolio">
			See Our Portfolio
			<svg xmlns="http://www.w3.org/2000/svg" width="26" height="20"><g fill="none" fill-rule="evenodd" stroke="white" stroke-width="2"><path d="M15 1l9 9-9 9M0 10h24"></path></g></svg>
		</a>
	</div>
	<div class="controls">
		<button id="{currentProject == 0 ? 'active' : ''}" on:click="{() => (currentProject = 0)}">01</button>
		<button id="{currentProject == 1 ? 'active' : ''}" on:click="{() => (currentProject = 1)}">02</button>
		<button id="{currentProject == 2 ? 'active' : ''}" on:click="{() => (currentProject = 2)}">03</button>
		<button id="{currentProject == 3 ? 'active' : ''}" on:click="{() => (currentProject = 3)}">04</button>
	</div>
</section>

<style>
	section {
		width: 100%;
		height: 720px;
		background-color: rgb(52, 101, 173);
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		position: relative;

		& .wrapper {
			width: 100%;
			height: 100%;
			background-color: rgba(0, 0, 0, 0.425);
			padding: 11.5rem;
			display: flex;
			flex-direction: column;
			gap: 2.25rem;

			@media (max-width: 1050px) {
				justify-content: center;
				padding: 3rem;
			}
		}

		@media (max-width: 573px) {
			width: 100vw;
		}
	}

	h2,
	p {
		width: 544px;
		color: white;
		margin: 0.5rem 0;

		@media (max-width: 1050px) {
			width: 100%;
		}
	}

	.controls {
		position: absolute;
		display: flex;
		bottom: 0;
		left: -5rem;

		& button {
			width: 5rem;
			aspect-ratio: 1;
			padding: 0;
			display: flex;
			align-items: center;
			justify-content: center;
			color: var(--lightGrey);
			background-color: white;
			border: 1px solid white;

			&#active {
				background-color: var(--darkBlue);
				color: white;
				pointer-events: none;
				border: 1px solid var(--darkBlue);
			}

			&:hover {
				background-color: var(--veryLightGrey);
			}
		}

		@media (max-width: 1050px) {
			display: none;
		}
	}
</style>
