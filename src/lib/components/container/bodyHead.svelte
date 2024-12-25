<script lang="ts">
	import * as Card from '@/components/ui/card';
	import TechCarousel from '@/components/layout/techCarousel.svelte';
	import BodyAbout from '@/components/layout/bodyAbout.svelte';
</script>

<Card.Root>
	<Card.Header class="rounded-t-sm bg-black dark:bg-white">
		<TechCarousel />
	</Card.Header>
	<Card.Content>
		<BodyAbout />
	</Card.Content>
	<Card.Footer>
		<!-- Social Link -->
	</Card.Footer>
</Card.Root>
