<script lang="ts">
	import * as Card from '@/components/ui/card';
	import { MapPin, School, GraduationCap } from 'lucide-svelte';

	const info = [
		{
			icon: School,
			title: 'Freshmen - Senior',
			description: 'Tabaco National High School'
		},
		{
			icon: GraduationCap,
			title: 'BS in Information Technology',
			description: 'STI College Legazpi'
		},
		{
			icon: MapPin,
			title: 'Location',
			description: 'Tabaco City, Albay, Philippines'
		}
	];
</script>

<Card.Root>
	<Card.Header>
		<Card.Title>About</Card.Title>
		<Card.Description>
			<p class="text-sm">
				Seeking opportunities to apply my skills in a dynamic environment and contribute to
				impactful projects.
			</p>
		</Card.Description>
	</Card.Header>
	<Card.Content class="space-y-3">
		{#each info as { icon, title, description }}
			<div class="flex items-center gap-3">
				<svelte:component this={icon} class="size-4" />
				<div class="flex flex-col">
					<p class="text-base font-semibold">{description}</p>
					<h1 class="text-xs font-light">{title}</h1>
				</div>
			</div>
		{/each}
	</Card.Content>
</Card.Root>
