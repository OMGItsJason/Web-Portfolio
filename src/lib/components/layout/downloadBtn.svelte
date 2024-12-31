<script lang="ts">
	import { Button } from '@/components/ui/button';
	import Download from 'lucide-svelte/icons/download';
	import * as Tooltip from '@/components/ui/tooltip';

	const downloadCV = () => {
		// src/lib/file/MyResume.pdf
		const fileUrl = './MyResume.pdf';
		const anchor = document.createElement('a');
		anchor.href = fileUrl;
		anchor.download = 'Jason Maliquid Resume.pdf';
		anchor.click();
	};
</script>

<div class="md:hidden">
	<Tooltip.Provider>
		<Tooltip.Root>
			<Tooltip.Trigger>
				<Button variant="outline" size="icon" onclick={downloadCV}>
					<Download />
				</Button>
			</Tooltip.Trigger>
			<Tooltip.Content>
				<p>Download CV</p>
			</Tooltip.Content>
		</Tooltip.Root>
	</Tooltip.Provider>
</div>

<div class="hidden md:block">
	<Button variant="default" onclick={downloadCV}>
		<Download />
		<p>Download CV</p>
	</Button>
</div>
