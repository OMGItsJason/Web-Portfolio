<script lang="ts">
	import HeaderNav from '@/components/layout/headerNav.svelte';
	import Logo from '@/assets/logo/Logo.png';
</script>

<header
	class="flex w-dvw items-center justify-between border-b px-3 py-2 shadow-xl dark:shadow-white/10"
>
	<img src={Logo} alt="Logo" class="size-11" />
	<HeaderNav />
</header>
