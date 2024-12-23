<script lang="ts">
	import Sun from 'lucide-svelte/icons/sun';
	import Moon from 'lucide-svelte/icons/moon';
	import Mail from 'lucide-svelte/icons/mail';
	import Phone from 'lucide-svelte/icons/phone';
	import * as Dialog from '$lib/components/ui/dialog';
	import { toggleMode } from 'mode-watcher';
	import { Button } from '$lib/components/ui/button';
</script>

<nav>
	<Button onclick={toggleMode} variant="outline" size="icon">
		<Sun
			class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
		/>
		<Moon
			class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
		/>
		<span class="sr-only">Toggle theme</span>
	</Button>
	<Dialog.Root>
		<Button variant="outline" size="icon">
			<Mail class="h-[1.2rem] w-[1.2rem]" />
			<span class="sr-only">Send Email</span>
		</Button>
		<Dialog.Content>
			<Dialog.Header>
				<Dialog.Title>Are you sure absolutely sure?</Dialog.Title>
				<Dialog.Description>
					This action cannot be undone. This will permanently delete your account and remove your
					data from our servers.
				</Dialog.Description>
			</Dialog.Header>
		</Dialog.Content>
	</Dialog.Root>
	<Dialog.Root>
		<Button variant="outline" size="icon">
			<Phone class="h-[1.2rem] w-[1.2rem]" />
			<span class="sr-only">Contact</span>
		</Button>
		<Dialog.Content>
			<Dialog.Header>
				<Dialog.Title>Are you sure absolutely sure?</Dialog.Title>
				<Dialog.Description>
					This action cannot be undone. This will permanently delete your account and remove your
					data from our servers.
				</Dialog.Description>
			</Dialog.Header>
		</Dialog.Content>
	</Dialog.Root>
</nav>
