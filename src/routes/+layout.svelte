<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { ModeWatcher } from 'mode-watcher';
	import * as Card from '@/components/ui/card';
	import Header from '@/components/container/header.svelte';
	import BodyHead from '@/components/container/bodyHead.svelte';
	import BodyNav from '@/components/container/bodyNav.svelte';
	import About from '@/components/container/about.svelte';
</script>

<ModeWatcher />
<div class="w-svw">
	<Header />
	<div class="space-y-3 p-2 md:px-10 2xl:px-20">
		<BodyHead />
		<BodyNav />
		<div class="grid space-y-3 md:grid-cols-2 md:space-x-3 md:space-y-0">
			<About />
			<Card.Root class="md:p-5">
				{@render children()}
			</Card.Root>
		</div>
	</div>
</div>
