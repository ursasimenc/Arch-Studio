<script>
	export let classes = "";
	export let title = "";
	export let desc = "";
	export let number = "";
</script>

<div id="card" class="{classes}">
	<div class="wrapper">
		{#if number !== ""}
			<div class="number">{number}</div>
		{/if}
		<div class="content">
			<h3>{title}</h3>
			{#if number === ""}
				<p>{desc}</p>
			{:else}
				<a href="/portfolio">{desc}</a>
			{/if}
		</div>
	</div>
</div>

<style>
	#card {
		width: 350px;
		height: 560px;
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;

		@media (max-width: 1050px) {
			width: 100%;
			height: 240px;
		}

		@media (max-width: 576px) {
			aspect-ratio: 22/17;
			width: 100%;
			height: auto;
		}
	}

	.wrapper {
		width: 100%;
		height: 100%;
		background: linear-gradient(#00000000, #0000007f);
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		padding: 2rem;
		position: relative;
		color: white;

		&:hover {
			background: rgba(211, 211, 211, 0.5);
		}

		& h3,
		a,
		p {
			margin: 0;
		}

		& a,
		p {
			color: #fff;
			font-family: League Spartan;
			font-size: 1.125rem;
			font-style: normal;
			font-weight: 500;
			line-height: 1.5rem; /* 133.333% */
			text-decoration: none;
			opacity: 0.75;
		}

		& .content {
			display: flex;
			flex-direction: column;
			justify-content: flex-end;
			height: 30%;
		}

		& .number {
			color: #fff;
			text-align: right;
			font-family: League Spartan;
			font-size: 15.625rem;
			font-style: normal;
			font-weight: 700;
			line-height: 12.5rem; /* 80% */
			letter-spacing: -0.3125rem;
			opacity: 0.5;
			height: 70%;
			position: absolute;
			top: 4rem;
			right: -0.7rem;

			@media (max-width: 1050px) {
				top: 50%;
				transform: translateY(-50%);
				right: 1.5rem;
			}

			@media (max-width: 576px) {
				display: none;
			}
		}
	}
</style>
