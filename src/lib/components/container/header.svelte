<script lang="ts">
	import HeaderNav from '@/components/layout/headerNav.svelte';
	import SearchBar from '@/components/layout/searchBar.svelte';
	import Logo from '@/assets/logo/Logo.png?enhanced';
</script>

<header
	class="flex w-dvw items-center justify-between border-b px-3 py-2 shadow-xl dark:shadow-white/10"
>
	<a href="/" aria-label="Home">
		<enhanced:img src={Logo} alt="Logo" class="size-8" />
	</a>
	<SearchBar />
	<HeaderNav />
</header>
