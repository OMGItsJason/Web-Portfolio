<script lang="ts">
	import { toggleMode } from 'mode-watcher';
	import { Button } from '@/components/ui/button';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu';
	import SquareUser from 'lucide-svelte/icons/square-user';
	import Sun from 'lucide-svelte/icons/sun';
	import Moon from 'lucide-svelte/icons/moon';
</script>

<div class="flex items-center">
	<Button onclick={toggleMode} variant="outline" size="icon" class="border-0 hover:bg-transparent">
		<Sun
			class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
		/>
		<Moon
			class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
		/>
		<span class="sr-only">Toggle theme</span>
	</Button>
	<DropdownMenu.Root>
		<DropdownMenu.Trigger>
			<SquareUser class="h-[1.2rem] w-[1.2rem]" />
		</DropdownMenu.Trigger>
		<DropdownMenu.Content>
			<DropdownMenu.Group>
				<DropdownMenu.GroupHeading>Contact Me</DropdownMenu.GroupHeading>
				<DropdownMenu.Separator />
				<DropdownMenu.Item>Profile</DropdownMenu.Item>
				<DropdownMenu.Item>Billing</DropdownMenu.Item>
				<DropdownMenu.Item>Team</DropdownMenu.Item>
				<DropdownMenu.Item>Subscription</DropdownMenu.Item>
			</DropdownMenu.Group>
		</DropdownMenu.Content>
	</DropdownMenu.Root>
</div>
