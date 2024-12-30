<script lang="ts">
	import * as Card from '@/components/ui/card';
	import { Button } from '@/components/ui/button';
	import { Separator } from '@/components/ui/separator';

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
	<Card.Header class="flex items-center p-2 text-center md:items-start md:text-left">
		<Card.Title class="flex p-0">
			{#each navItem as item}
				<Button href={item.href} variant="link" class="md:text-lg">{item.title}</Button>
				<Separator orientation="vertical" />
			{/each}
		</Card.Title>
	</Card.Header>
</Card.Root>
