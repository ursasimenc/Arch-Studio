<script>
	import JakeImg from "$lib/assets/about/desktop/avatar-jake.jpg";
	import ThomsponImg from "$lib/assets/about/desktop/avatar-thompson.jpg";
	import JacksonImg from "$lib/assets/about/desktop/avatar-jackson.jpg";
	import MariaImg from "$lib/assets/about/desktop/avatar-maria.jpg";

	const team = [
		{
			name: "Jake Richards",
			role: "Chief Architect",
			img: JakeImg,
		},
		{
			name: "Thompson Smith",
			role: "Head of Finance",
			img: ThomsponImg,
		},
		{
			name: "Jackson Rourke",
			role: "Lead Designer",
			img: JacksonImg,
		},
		{
			name: "Maria Simpson",
			role: "Senior Architect",
			img: MariaImg,
		},
	];

	export let teamMember = 0;
</script>

<div id="leader">
	<div>
		<img src="{team[teamMember].img}" alt="{`${team[teamMember].name}`}" />
		<div id="leader-hover">
			<svg xmlns="http://www.w3.org/2000/svg" width="40" height="33"
				><path
					fill="white"
					d="M40 4.262a16.384 16.384 0 01-4.713 1.291 8.22 8.22 0 003.608-4.54 16.44 16.44 0 01-5.212 1.992 8.193 8.193 0 00-5.99-2.592c-5.298 0-9.191 4.944-7.995 10.075C12.88 10.147 6.833 6.88 2.785 1.915.635 5.603 1.67 10.428 5.323 12.872a8.172 8.172 0 01-3.715-1.027c-.09 3.802 2.635 7.358 6.582 8.15a8.225 8.225 0 01-3.707.14 8.213 8.213 0 007.667 5.698A16.5 16.5 0 010 29.233a23.232 23.232 0 0012.58 3.687c15.237 0 23.845-12.868 23.325-24.41A16.708 16.708 0 0040 4.262z"
				></path></svg
			><svg xmlns="http://www.w3.org/2000/svg" width="40" height="40"
				><path
					fill="white"
					d="M36 0H4C1.8 0 0 1.8 0 4v32c0 2.2 1.8 4 4 4h32c2.2 0 4-1.8 4-4V4c0-2.2-1.8-4-4-4zM12 34H6V16h6v18zM9 12.6C7 12.6 5.4 11 5.4 9S7 5.4 9 5.4 12.6 7 12.6 9 11 12.6 9 12.6zM34 34h-6V23.4c0-1.6-1.4-3-3-3s-3 1.4-3 3V34h-6V16h6v2.4c1-1.6 3.2-2.8 5-2.8 3.8 0 7 3.2 7 7V34z"
				></path></svg
			>
		</div>
	</div>
	<div>
		<h4>{team[teamMember].name}</h4>
		<p>{team[teamMember].role}</p>
	</div>
</div>

<style>
	#leader {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}
	h4,
	p {
		margin: 0;
	}

	div:has(img) {
		position: relative;
	}

	img {
		width: 254px;
		height: auto;
		object-fit: cover;
		filter: contrast(1.15) brightness(0.9);

		@media (max-width: 576px) {
			width: 100%;
		}
	}

	#leader-hover {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 2rem;
		background-color: rgba(0, 0, 0, 0.5);
		opacity: 0;

		& svg {
			cursor: pointer;
		}
	}

	#leader:hover #leader-hover {
		opacity: 1;
	}
</style>
