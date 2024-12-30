<script lang="ts">
	import * as Command from '@/components/ui/command';
	import CommandGroup from '../ui/command/command-group.svelte';

	let searchOpen: boolean = $state(false);

	const searchItems = [
		{ name: 'About', href: '/' },
		{ name: 'Tech Stack', href: '/' },
		{ name: 'Projects', href: '/projects' },
		{ name: 'Certificates', href: '/certificates' }
	];
</script>

<div class="relative hidden w-[50rem] md:block">
	<Command.Root class="border-2">
		<Command.Input
			onclick={() => {
				searchOpen = !searchOpen;
			}}
			placeholder="Search..."
		/>
		{#if searchOpen}
			<Command.List
				class="absolute left-0 right-0 top-10 z-50 w-full rounded-t-sm border-2 bg-white dark:bg-black"
			>
				<Command.Empty>No results found.</Command.Empty>
				<CommandGroup heading="Recommended">
					{#each searchItems as item}
						<Command.Item onclick={() => (window.location.href = item.href)} class="cursor-pointer">
							<a href={item.href}>{item.name}</a>
						</Command.Item>
					{/each}
				</CommandGroup>
			</Command.List>
		{/if}
	</Command.Root>
</div>
