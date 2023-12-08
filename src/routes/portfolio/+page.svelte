<script>
	import ProjectCard from "$lib/components/ProjectCard/ProjectCard.svelte";
</script>

<svelte:head>
	<title>Portfolio</title>
</svelte:head>

<main>
	<div>
		<ProjectCard classes="seraph" title="Seraph Station" desc="September 2019" number="" />
		<ProjectCard classes="eebox" title="Eebox Building" desc="August 2017" number="" />
		<ProjectCard classes="federal" title="Federal II Tower" desc="March 2017" number="" />
	</div>
	<div>
		<ProjectCard classes="del-sol" title="Project Del Sol" desc="January 2016 " number="" />
		<ProjectCard classes="prototype" title="Le Prototype" desc="October 2015" number="" />
		<ProjectCard classes="twotwoeight" title="228B Tower" desc="April 2015" number="" />
	</div>
	<div>
		<ProjectCard classes="edelweiss" title="Grand Edelweiss Hotel" desc="December 2013" number="" />
		<ProjectCard classes="netcry " title="Netcry Tower" desc="August 2012" number="" />
		<ProjectCard classes="hypers" title="Hypers" desc="January 2012" number="" />
	</div>
	<div>
		<ProjectCard classes="sxiv" title="SXIV Tower" desc="March 2011" number="" />
		<ProjectCard classes="trinity" title="Trinity Bank Tower" desc="September 2010" number="" />
		<ProjectCard classes="paramour" title="Project Paramour" desc="February 2008" number="" />
	</div>
</main>

<style>
	main {
		width: 100%;
		max-width: var(--maxWidth);
		display: flex;
		flex-direction: column;
		gap: 2rem;

		@media (max-width: 1050px) {
			max-width: var(--maxWidthTablet);
		}

		& > div {
			width: 100%;
			display: flex;
			justify-content: space-between;

			@media (max-width: 1050px) {
				flex-direction: column;
				gap: 2rem;
			}

			@media (max-width: 576px) {
				padding-inline: 2rem;
			}
		}
	}
</style>
