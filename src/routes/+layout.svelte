<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { ModeWatcher } from 'mode-watcher';
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
		<div class="grid">
			<About />
			{@render children()}
		</div>
	</div>
</div>
