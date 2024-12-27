<script lang="ts">
	import * as Card from '@/components/ui/card';
	import { Button } from '@/components/ui/button';

	const navItem = [
		{
			title: 'Experience',
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
		<Card.Title class="flex p-0">
			{#each navItem as item}
				<Button href={item.href} variant="link">{item.title}</Button>
			{/each}
		</Card.Title>
	</Card.Header>
</Card.Root>
