<script lang="ts">
	import * as Card from '@/components/ui/card';
	import TechCarousel from '@/components/layout/techCarousel.svelte';
	import BodyAbout from '@/components/layout/bodyAbout.svelte';
	import HeadFooter from '@/components/container/headFooter.svelte';
</script>

<Card.Root>
	<Card.Header class="rounded-t-sm bg-black dark:bg-white">
		<TechCarousel />
	</Card.Header>
	<Card.Content class="pb-2">
		<BodyAbout />
	</Card.Content>
	<Card.Footer class="pb-2">
		<HeadFooter />
	</Card.Footer>
</Card.Root>
