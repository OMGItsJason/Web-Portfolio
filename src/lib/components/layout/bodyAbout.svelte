<script lang="ts">
	import { Skeleton } from '@/components/ui/skeleton';
	import DownloadBtn from '@/components/layout/downloadBtn.svelte';

	let imgLoad: boolean = $state(true);

	const handleLoad = () => {
		imgLoad = false;
	};
</script>

<div>
	{#if imgLoad}
		<Skeleton class="size-16 rounded-full" />
	{/if}
	<div class="flex justify-between md:items-center">
		<div class="md:flex md:items-center md:space-x-3">
			<img
				src="https://utfs.io/f/roenevQjcYdljmkmKT7gDvIJ3SXLwezUhRN40y1Zc6x2aCnp"
				alt="@jasonm2822"
				onload={handleLoad}
				class="size-16 rounded-full md:size-28"
				style:display={imgLoad ? 'none' : 'block'}
			/>
			<div>
				<h1 class=" text-2xl font-bold md:text-4xl">Jason Maliquid</h1>
				<p class="motion-preset-typewriter-[24] text-sm font-normal md:text-xl">
					Aspiring Frontend Web Developer
				</p>
			</div>
		</div>
		<div>
			<DownloadBtn />
		</div>
	</div>
</div>
