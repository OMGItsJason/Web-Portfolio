<script lang="ts">
	import { Button } from '@/components/ui/button';
	import Download from 'lucide-svelte/icons/download';
	import * as Tooltip from '@/components/ui/tooltip';
</script>

<div class="md:hidden">
	<Tooltip.Provider>
		<Tooltip.Root>
			<Tooltip.Trigger>
				<Button variant="outline" size="icon">
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
	<Button variant="default">
		<Download />
		<p>Download CV</p>
	</Button>
</div>
