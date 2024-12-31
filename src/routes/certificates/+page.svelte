<script lang="ts">
	import JavaFoundCert from '@/assets/certificates/JavaFoundationCertificate.png?enhanced';
	import SystemAdCert from '@/assets/certificates/SystemAdministrationCertificate.png?enhanced';

	const certificates = [
		{
			name: 'Java Foundation Certificate',
			image: JavaFoundCert,
			alt: 'Java Foundation Certificate'
		},
		{
			name: 'System Administration Certificate',
			image: SystemAdCert,
			alt: 'System Administration Certificate'
		}
	];
</script>

<div class="grid grid-rows-[1fr,auto] gap-3">
	<h1 class="text-xl font-bold md:text-3xl">CERTIFICATES</h1>
	<div class="grid gap-3 text-center md:grid-cols-2">
		{#each certificates as cert}
			<a href="/" class="h-52 w-full md:h-64">
				<enhanced:img src={cert.image} alt={cert.alt} class="h-full w-full object-fill" />
				<span class="hidden md:block">{cert.name}</span>
			</a>
		{/each}
	</div>
</div>
