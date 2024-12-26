<script lang="ts">
	import * as Card from '@/components/ui/card';

	const navItem = [
		{
			title: 'Tech-Stack',
			href: '/'
		},
		{
			title: 'Projects',
			href: '/projects'
		},
		{
			title: 'Certificates',
			href: '/certificates'
		}
	];
</script>

<Card.Root>
	<Card.Header class="flex items-center p-2 text-center">
		<Card.Title class="flex gap-5 p-0">
			{#each navItem as item}
				<a href={item.href} class="text-base">{item.title}</a>
			{/each}
		</Card.Title>
	</Card.Header>
</Card.Root>
