<script lang="ts">
	import Animez from '@/assets/projects/Animez.png?enhanced';
	import NetflixClone from '@/assets/projects/NetflixClone.png?enhanced';
	import VotingSystem from '@/assets/projects/VotingSystemProject.png?enhanced';
	import VSHR from '@/assets/projects/VSHR.png?enhanced';

	const projects = [
		{
			img: VotingSystem,
			project: 'Voting System',
			link: 'https://github.com/OMGItsJason/Voting-System-V2'
		},
		{
			img: Animez,
			project: 'Animez',
			link: 'https://github.com/OMGItsJason/Animez'
		},
		{
			img: NetflixClone,
			project: 'Netflix Clone',
			link: 'https://github.com/OMGItsJason/Netflix-Clone'
		},
		{
			img: VSHR,
			project: 'Online Reservation System With 360 View',
			link: 'https://villa-salome-hotel-and-resort.vercel.app/'
		}
	];
</script>

<div class=" grid grid-rows-[1fr,auto,2fr] gap-3">
	<h1 class="text-xl font-bold md:text-3xl">FEATURED PROJECTS</h1>
	<div class="grid place-content-center gap-3 text-center md:row-start-2 md:grid-cols-4">
		{#each projects as project}
			<a
				href={project.link}
				aria-label={project.project}
				class="h-full w-full text-sm font-medium md:text-base"
				target="_blank"
			>
				<enhanced:img
					src={project.img}
					alt={project.project}
					class="h-[180px] w-full rounded-sm object-fill md:h-full"
				/>
				<span class="hidden text-base font-medium md:block">{project.project}</span>
			</a>
		{/each}
	</div>
	<a
		href="https://github.com/OMGItsJason"
		class="mt-auto text-center font-medium underline underline-offset-4 md:text-sm">More Projects</a
	>
</div>
