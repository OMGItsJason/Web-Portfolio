<script lang="ts">
	import JavaFoundCert from '@/assets/certificates/JavaFoundationCertificate.png?enhanced';
	import SystemAdCert from '@/assets/certificates/SystemAdministrationCertificate.png?enhanced';
	import { Button } from '@/components/ui/button';
	import * as Dialog from '@/components/ui/dialog';

	const certificates = [
		{
			name: 'Java Foundation',
			image: JavaFoundCert,
			alt: 'Java Foundation'
		},
		{
			name: 'System Administration',
			image: SystemAdCert,
			alt: 'System Administration'
		}
	];

	let selectedCertificate: boolean = $state(false);
	// svelte-ignore non_reactive_update
	let currentCert = certificates[0];

	const viewSelectedCertificate = (cert: any) => {
		currentCert = cert;
		selectedCertificate = true;
	};
</script>

<div class="grid grid-rows-[1fr,auto] gap-3">
	<h1 class="text-xl font-bold md:text-3xl">CERTIFICATES</h1>
	<div class="grid gap-3 text-center md:grid-cols-2">
		{#each certificates as cert}
			<Button
				variant="ghost"
				onclick={() => viewSelectedCertificate(cert)}
				class="h-52 w-full md:h-full"
			>
				<enhanced:img src={cert.image} alt={cert.alt} class="h-full w-full object-fill" />
			</Button>
		{/each}
	</div>
</div>

<Dialog.Root bind:open={selectedCertificate}>
	<Dialog.Content class="max-w-3xl">
		<Dialog.Header>
			<Dialog.Title>{currentCert.name}</Dialog.Title>
		</Dialog.Header>
		<enhanced:img src={currentCert.image} alt={currentCert.alt} class="h-full w-full object-fill" />
	</Dialog.Content>
</Dialog.Root>
