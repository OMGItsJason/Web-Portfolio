<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { ModeWatcher } from 'mode-watcher';
	import Header from '@/components/container/header.svelte';
</script>

<ModeWatcher />
<div class="w-svw">
	<Header />
	<div></div>
</div>
{@render children()}
