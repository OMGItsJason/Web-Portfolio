<script lang="ts">
	import { Facebook, Instagram, Github } from 'lucide-svelte';
	import { Button } from '@/components/ui/button';

	const Links = [
		{
			icon: Facebook,
			href: 'https://www.facebook.com/maliquid.jason',
			label: 'Facebook'
		},
		{
			icon: Instagram,
			href: 'https://www.instagram.com/itz.me_jason',
			label: 'Instagram'
		},
		{
			icon: Github,
			href: 'https://www.github.com/OMGItsJason',
			label: 'Github'
		}
	];
</script>

<div class="hidden md:flex">
	{#each Links as { icon, href, label }}
		<Button variant="ghost" {href} target="_blank" class="flex items-center md:text-lg">
			<svelte:component this={icon} />
			<span>
				{label}
			</span>
		</Button>
	{/each}
</div>
<div class="flex gap-2 md:hidden">
	{#each Links as { icon, href }}
		<Button variant="outline" size="icon" {href} target="_blank">
			<svelte:component this={icon} />
		</Button>
	{/each}
</div>
