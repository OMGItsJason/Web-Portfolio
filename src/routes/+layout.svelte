<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { ModeWatcher } from 'mode-watcher';
	import Header from '@/components/container/header.svelte';
	import BodyHead from '@/components/container/bodyHead.svelte';
</script>

<ModeWatcher />
<div class="w-svw">
	<Header />
	<div class="p-2 md:px-10 2xl:px-20">
		<BodyHead />
	</div>
</div>
{@render children()}
