<script lang="ts">
	import HeaderNav from '@/components/layout/headerNav.svelte';
	import SearchBar from '@/components/layout/searchBar.svelte';
	import { Skeleton } from '@/components/ui/skeleton';
	import Logo from '@/assets/logo/Logo.png?enhanced';

	let loading: boolean = $state(true);

	const handleLoad = () => {
		loading = false;
	};
</script>

<header
	class="flex w-dvw items-center justify-between border-b px-3 py-2 shadow-xl dark:shadow-white/10"
>
	{#if loading}
		<Skeleton class="size-8 rounded-full" />
	{/if}
	<a href="/" aria-label="Home">
		<enhanced:img
			src={Logo}
			alt="Logo"
			class="size-8"
			style:display={loading ? 'none' : 'block'}
			onload={handleLoad}
		/>
	</a>

	<SearchBar />
	<HeaderNav />
</header>
