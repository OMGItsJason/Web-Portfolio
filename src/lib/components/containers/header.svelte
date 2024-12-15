<script lang="ts">
	import Logo from '@/assets/logo/logo.png';
	import Navigation from '@/components/containers/nav.svelte';
</script>

<header class="flex items-center justify-between p-2 shadow-md">
	<img src={Logo} alt="Logo" class="size-10 rounded-lg" />
	<nav>
		<Navigation />
	</nav>
</header>
