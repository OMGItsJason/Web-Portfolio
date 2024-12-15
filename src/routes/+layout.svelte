<script lang="ts">
	import '../app.css';
	import Header from '@/components/containers/header.svelte';
	import { ModeWatcher } from 'mode-watcher';
	let { children } = $props();
</script>

<ModeWatcher />
<div class="w-svw">
	<Header />
</div>
{@render children()}
