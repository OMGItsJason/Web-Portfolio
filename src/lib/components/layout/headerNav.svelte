<script lang="ts">
	import Sun from 'lucide-svelte/icons/sun';
	import Moon from 'lucide-svelte/icons/moon';
	import Mail from 'lucide-svelte/icons/mail';
	import FileCode from 'lucide-svelte/icons/file-code';
	import * as Dialog from '@/components/ui/dialog';
	import { toggleMode } from 'mode-watcher';
	import { Button } from '@/components/ui/button';
	import { Textarea } from '@/components/ui/textarea';
	import { Input } from '@/components/ui/input';
	import { Label } from '@/components/ui/label';
	import * as DropdownMenu from '@/components/ui/dropdown-menu';
	import DropdownMenuItem from '@/components/ui/dropdown-menu/dropdown-menu-item.svelte';
</script>

<nav class="flex items-center space-x-1">
	<!-- Theme -->
	<Button onclick={toggleMode} variant="outline" size="icon">
		<Sun
			class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
		/>
		<Moon
			class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
		/>
		<span class="sr-only">Toggle theme</span>
	</Button>
	<!-- Send Email -->
	<Dialog.Root>
		<Dialog.Trigger>
			<Button variant="outline" size="icon">
				<Mail class="h-[1.2rem] w-[1.2rem]" />
				<span class="sr-only">Send Email</span>
			</Button>
		</Dialog.Trigger>
		<Dialog.Content>
			<Dialog.Header>
				<Dialog.Title class="text-center">Send Email</Dialog.Title>
				<Dialog.Description>
					<form action="?submit" method="post" class="space-y-3 text-left">
						<div>
							<Label for="email">Email:</Label>
							<Input
								type="email"
								id="email"
								name="email"
								autocomplete="off"
								placeholder="Email"
								required
								class="focus-visible:ring-0"
							/>
						</div>
						<div>
							<Label for="subject">Subject:</Label>
							<Input
								type="text"
								id="subject"
								name="subject"
								placeholder="Subject"
								class="focus-visible:ring-0"
								required
							/>
						</div>
						<div>
							<Label for="message">Message:</Label>
							<Textarea
								id="message"
								name="message"
								placeholder="Message"
								class="min-h-52 resize-none focus-visible:ring-0"
								required
							/>
						</div>
						<div class="flex justify-end">
							<Button type="submit">Send</Button>
						</div>
					</form>
				</Dialog.Description>
			</Dialog.Header>
		</Dialog.Content>
	</Dialog.Root>
	<!-- Built With -->
	<DropdownMenu.Root>
		<DropdownMenu.Trigger>
			<Button variant="outline" size="icon">
				<FileCode class="h-[1.2rem] w-[1.2rem]" />
				<span class="sr-only">Built With</span>
			</Button>
		</DropdownMenu.Trigger>
		<DropdownMenu.Content>
			<DropdownMenu.Group>
				<DropdownMenu.GroupHeading>Built With</DropdownMenu.GroupHeading>
				<DropdownMenu.Separator />
				<DropdownMenu.Item>
					<a href="https://svelte.dev/" class="flex items-center" target="_blank">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							x="0px"
							y="0px"
							width="48"
							height="48"
							viewBox="0 0 48 48"
						>
							<path
								fill="#ef4823"
								d="M40.311,8.7C36.352,2.998,27.6,0.647,21.934,4.243l-9.987,6.392	c-2.724,1.707-4.612,4.503-5.157,7.663c-0.472,2.651,0.991,4.848,2.262,7.208c-0.872,1.307-2.516,3.287-2.77,4.813	c-0.581,3.232,0.182,6.573,2.07,9.225c3.995,5.702,11.914,7.741,17.579,4.146l9.913-6.724c2.724-1.707,4.612-4.503,5.157-7.663	c0.472-2.651,0.073-5.375-1.198-7.736c0.872-1.307,1.453-2.76,1.707-4.285C42.127,14.012,42.235,11.351,40.311,8.7"
							></path><path
								fill="#010101"
								d="M19.64,45.946c-1.064,0-2.149-0.13-3.234-0.393c-3.425-0.831-6.42-2.871-8.433-5.744	c-1.962-2.754-2.745-6.244-2.147-9.572c0.216-1.297,1.316-2.837,2.201-4.074c0.172-0.24,0.336-0.47,0.484-0.684	c-0.101-0.185-0.203-0.37-0.304-0.553c-1.14-2.065-2.319-4.2-1.872-6.709c0.566-3.284,2.523-6.192,5.367-7.974l9.984-6.39	c5.748-3.648,14.804-1.465,19.003,4.579c1.957,2.698,1.94,5.418,1.277,8.93c-0.251,1.501-0.798,2.922-1.627,4.23	c1.198,2.357,1.596,5.112,1.119,7.792c-0.566,3.281-2.519,6.187-5.36,7.969l-9.906,6.72c-0.004,0.003-0.008,0.005-0.012,0.008	C24.236,45.314,21.987,45.946,19.64,45.946z M28.218,2.986c-2.167,0-4.269,0.527-6.034,1.647l-9.986,6.391	c-2.625,1.645-4.429,4.324-4.951,7.352c-0.39,2.189,0.66,4.09,1.77,6.102c0.148,0.268,0.297,0.537,0.443,0.809	c0.081,0.151,0.072,0.334-0.022,0.476c-0.192,0.288-0.418,0.604-0.657,0.939c-0.829,1.159-1.86,2.602-2.042,3.693	c-0.556,3.09,0.17,6.325,1.991,8.88c3.953,5.642,11.553,7.446,16.948,4.027l9.907-6.72c0.005-0.003,0.009-0.006,0.014-0.009	c2.622-1.643,4.425-4.322,4.947-7.349c0.458-2.57,0.049-5.211-1.15-7.438c-0.081-0.151-0.072-0.334,0.022-0.476	c0.842-1.263,1.392-2.644,1.636-4.105c0.001-0.003,0.001-0.007,0.002-0.01c0.634-3.359,0.655-5.781-1.119-8.223	c-0.002-0.003-0.004-0.005-0.006-0.008C37.295,5.166,32.624,2.986,28.218,2.986z"
							></path><path
								fill="#d6e5e5"
								d="M20.974,40.088c-3.232,0.835-6.61-0.436-8.498-3.16c-1.162-1.598-1.598-3.595-1.271-5.557	c0.073-0.327,0.145-0.617,0.218-0.944l0.256-0.938l0.508,0.363c1.198,0.872,2.432,1.882,3.848,2.318l0.363,0.109l-0.036,0.363	c-0.036,0.508,0.109,1.053,0.399,1.489c0.581,0.835,2.086,1.3,3.067,1.046c0.218-0.073,0.436-0.145,0.617-0.254l10.19-6.182	c0.508-0.327,0.567-1.206,0.676-1.787c0.109-0.581-0.036-1.198-0.363-1.671c-0.581-0.835-1.598-1.198-2.579-0.944	c-0.218,0.073-0.895,0.313-1.077,0.422l-3.813,2.433c-0.617,0.399-1.307,0.69-2.034,0.872c-3.232,0.835-6.61-0.436-8.498-3.16	c-1.126-1.598-1.531-4.31-1.168-6.271c0.327-1.889,1.489-3.595,3.123-4.612l9.92-5.641c0.617-0.399,1.307-0.69,2.034-0.908	c3.232-0.835,6.61,0.436,8.498,3.16c1.162,1.598,1.598,3.595,1.271,5.557c-0.073,0.327-0.145,0.617-0.254,0.944l-0.034,0.107	c-0.073,0.234-0.353,0.327-0.552,0.185l-0.105-0.075c-1.198-0.872-2.506-1.525-3.922-1.961l-0.363-0.109l0.036-0.363	c0.036-0.508-0.109-1.053-0.399-1.489c-0.581-0.835-1.688-1.122-2.668-0.868c-0.218,0.073-0.436,0.145-0.617,0.254l-9.861,6.279	c-0.508,0.327-0.835,0.799-0.944,1.38c-0.109,0.581,0.036,1.198,0.363,1.671c0.581,0.835,1.598,1.198,2.579,0.944	c0.218-0.073,0.436-0.145,0.617-0.254l3.813-2.433c0.617-0.399,1.307-0.69,2.034-0.908c3.232-0.835,6.986-0.553,8.875,2.171	c1.162,1.598,1.929,4.257,1.602,6.218c-0.327,1.889-1.489,3.595-3.123,4.612L23.007,39.18C22.39,39.58,21.7,39.87,20.974,40.088"
							></path><path
								fill="#010101"
								d="M18.981,40.806c-0.991,0-1.977-0.177-2.921-0.529c-1.609-0.6-2.979-1.665-3.961-3.08	c-1.224-1.685-1.704-3.781-1.35-5.901c0.001-0.008,0.003-0.016,0.005-0.024c0.037-0.165,0.073-0.322,0.11-0.478	c0.036-0.152,0.072-0.305,0.108-0.467c0.002-0.007,0.003-0.014,0.005-0.021l0.256-0.938c0.04-0.146,0.149-0.263,0.291-0.314	c0.143-0.051,0.301-0.029,0.424,0.059l0.508,0.363c0.17,0.123,0.336,0.247,0.505,0.371c1.015,0.752,2.065,1.529,3.21,1.881	l0.36,0.108c0.212,0.064,0.35,0.269,0.328,0.489l-0.036,0.356c-0.027,0.403,0.093,0.848,0.323,1.193	c0.439,0.63,1.724,1.064,2.551,0.858c0.194-0.065,0.376-0.126,0.51-0.207l4.798-3.358l5.384-2.818	c0.253-0.168,0.348-0.754,0.417-1.182c0.017-0.105,0.033-0.205,0.051-0.298c0.084-0.446-0.024-0.94-0.289-1.322	c-0.462-0.664-1.272-0.963-2.067-0.763c-0.344,0.115-0.855,0.309-0.965,0.372l-3.807,2.429c-0.647,0.419-1.378,0.732-2.17,0.93	c-1.672,0.432-3.412,0.342-5.027-0.261c-1.611-0.601-2.602-1.841-3.584-3.258c-1.282-1.82-1.976-4.535-1.622-6.446	c0.345-1.995,1.592-3.837,3.334-4.921c0.005-0.003,0.01-0.006,0.016-0.009l9.909-5.635c0.612-0.394,1.313-0.707,2.141-0.955	c0.006-0.002,0.011-0.003,0.017-0.005c1.675-0.433,3.415-0.343,5.031,0.26c1.609,0.6,2.979,1.665,3.961,3.08	c1.224,1.685,1.704,3.781,1.35,5.901c-0.001,0.008-0.003,0.016-0.005,0.024c-0.066,0.295-0.144,0.62-0.267,0.99l-0.031,0.099	c-0.078,0.251-0.274,0.451-0.523,0.534c-0.249,0.084-0.526,0.042-0.74-0.11l-0.105-0.075c-1.155-0.84-2.428-1.477-3.789-1.895	l-0.36-0.108c-0.212-0.064-0.35-0.269-0.328-0.489l0.036-0.356c0.028-0.409-0.09-0.843-0.323-1.193	c-0.432-0.621-1.298-0.897-2.152-0.681c-0.192,0.064-0.372,0.125-0.505,0.204l-5.253,3.042l-4.603,3.233	c-0.404,0.26-0.653,0.622-0.738,1.075c-0.084,0.446,0.024,0.94,0.289,1.322c0.462,0.664,1.273,0.964,2.067,0.763	c0.191-0.064,0.371-0.125,0.505-0.204l3.703-2.077c0.612-0.396,1.316-0.711,2.15-0.961c0.006-0.002-0.006,0.001,0,0	c1.814-0.469,3.61-0.562,5.162-0.26c1.824,0.354,3.284,1.256,4.223,2.606c1.308,1.801,2.119,4.207,1.786,6.21	c-0.347,2.004-1.594,3.845-3.335,4.929l-10.694,6.683c-0.608,0.394-1.312,0.709-2.146,0.959c-0.006,0.002-0.011,0.003-0.017,0.005	C20.394,40.716,19.686,40.806,18.981,40.806z M11.66,31.46c-0.309,1.871,0.114,3.716,1.191,5.196	c0.002,0.003,0.004,0.006,0.006,0.008c1.772,2.556,4.983,3.751,7.993,2.977c0.745-0.224,1.369-0.503,1.907-0.851l10.701-6.687	c1.522-0.947,2.611-2.554,2.913-4.299c0.292-1.75-0.466-3.922-1.625-5.515c-0.002-0.003-0.004-0.006-0.006-0.009	c-2.26-3.26-6.966-2.35-8.37-1.988c-0.745,0.224-1.368,0.502-1.907,0.851l-3.711,2.083c-0.004,0.002-0.007,0.005-0.011,0.007	c-0.225,0.135-0.471,0.217-0.709,0.296c-0.01,0.003-0.02,0.006-0.03,0.009c-1.178,0.305-2.385-0.137-3.075-1.128	c-0.409-0.59-0.568-1.326-0.438-2.02c0.132-0.703,0.529-1.286,1.149-1.684l4.613-3.24l5.25-3.04c0.003-0.002,0.007-0.004,0.01-0.006	c0.225-0.135,0.471-0.217,0.709-0.296c0.01-0.003,0.021-0.006,0.031-0.009c1.233-0.32,2.504,0.103,3.164,1.052	c0.351,0.526,0.524,1.173,0.481,1.783c1.455,0.448,2.815,1.127,4.045,2.019c0.1-0.304,0.165-0.567,0.232-0.866	c0.309-1.871-0.114-3.716-1.191-5.196c-0.002-0.003-0.004-0.006-0.006-0.009c-1.772-2.556-4.983-3.751-7.994-2.977	c-0.745,0.224-1.369,0.502-1.907,0.851c-0.007,0.005-0.015,0.009-0.023,0.014l-9.912,5.636c-1.517,0.947-2.603,2.552-2.904,4.294	c-0.366,1.979,0.482,4.351,1.47,5.752c1.776,2.561,4.611,3.93,7.624,3.152c0.697-0.174,1.334-0.447,1.898-0.812l3.816-2.435	c0.004-0.002,0.007-0.005,0.011-0.007c0.273-0.164,1.16-0.461,1.169-0.464c0.01-0.003,0.02-0.006,0.03-0.009	c1.178-0.305,2.385,0.137,3.075,1.128c0.409,0.59,0.568,1.326,0.438,2.02c-0.016,0.086-0.031,0.179-0.047,0.275	c-0.103,0.636-0.23,1.427-0.834,1.816c-0.003,0.002-0.007,0.004-0.01,0.006l-5.382,2.96l-4.809,3.222	c-0.227,0.136-0.472,0.218-0.71,0.297c-0.01,0.003-0.021,0.007-0.032,0.009c-1.201,0.311-2.899-0.275-3.563-1.229	c-0.351-0.526-0.524-1.173-0.481-1.783c-1.299-0.4-2.413-1.225-3.49-2.022c-0.154-0.114-0.307-0.227-0.46-0.339l-0.078,0.286	c-0.036,0.161-0.072,0.314-0.108,0.467C11.729,31.155,11.695,31.303,11.66,31.46z"
							></path>
						</svg>
						Svelte 5
					</a>
				</DropdownMenu.Item>
				<DropdownMenu.Item>
					<a href="https://tailwindcss.com/" class="flex items-center" target="_blank">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							x="0px"
							y="0px"
							width="48"
							height="48"
							viewBox="0 0 48 48"
						>
							<path
								fill="#00acc1"
								d="M24,9.604c-6.4,0-10.4,3.199-12,9.597c2.4-3.199,5.2-4.398,8.4-3.599 c1.826,0.456,3.131,1.781,4.576,3.247C27.328,21.236,30.051,24,36,24c6.4,0,10.4-3.199,12-9.598c-2.4,3.199-5.2,4.399-8.4,3.6 c-1.825-0.456-3.13-1.781-4.575-3.247C32.672,12.367,29.948,9.604,24,9.604L24,9.604z M12,24c-6.4,0-10.4,3.199-12,9.598 c2.4-3.199,5.2-4.399,8.4-3.599c1.825,0.457,3.13,1.781,4.575,3.246c2.353,2.388,5.077,5.152,11.025,5.152 c6.4,0,10.4-3.199,12-9.598c-2.4,3.199-5.2,4.399-8.4,3.599c-1.826-0.456-3.131-1.781-4.576-3.246C20.672,26.764,17.949,24,12,24 L12,24z"
							></path>
						</svg>
						TailwindCSS
					</a>
				</DropdownMenu.Item>
				<DropdownMenuItem>
					<a href="https://next.shadcn-svelte.com/" class="flex items-center" target="_blank">
						<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 256 256" class="size-6"
							><rect width="256" height="256" fill="none"></rect><line
								x1="208"
								y1="128"
								x2="128"
								y2="208"
								fill="none"
								stroke="#EB4F27"
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="16"
							></line><line
								x1="192"
								y1="40"
								x2="40"
								y2="192"
								fill="none"
								stroke="#EB4F27"
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="16"
							></line></svg
						>
						ShadCN
					</a>
				</DropdownMenuItem>
				<DropdownMenuItem>
					<a href="https://www.typescriptlang.org/" class="flex items-center" target="_blank">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							x="0px"
							y="0px"
							width="48"
							height="48"
							viewBox="0 0 48 48"
						>
							<rect width="36" height="36" x="6" y="6" fill="#1976d2"></rect><polygon
								fill="#fff"
								points="27.49,22 14.227,22 14.227,25.264 18.984,25.264 18.984,40 22.753,40 22.753,25.264 27.49,25.264"
							></polygon><path
								fill="#fff"
								d="M39.194,26.084c0,0-1.787-1.192-3.807-1.192s-2.747,0.96-2.747,1.986 c0,2.648,7.381,2.383,7.381,7.712c0,8.209-11.254,4.568-11.254,4.568V35.22c0,0,2.152,1.622,4.733,1.622s2.483-1.688,2.483-1.92 c0-2.449-7.315-2.449-7.315-7.878c0-7.381,10.658-4.469,10.658-4.469L39.194,26.084z"
							></path>
						</svg>
						TypeScript
					</a>
				</DropdownMenuItem>
				<DropdownMenuItem>
					<a href="https://vercel.com/" class="flex items-center" target="_blank">
						<svg
							width="76"
							height="65"
							viewBox="0 0 76 65"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
							><path d="M37.5274 0L75.0548 65H0L37.5274 0Z" fill="#d7d7d7" /></svg
						>
						Vercel
					</a>
				</DropdownMenuItem>
			</DropdownMenu.Group>
		</DropdownMenu.Content>
	</DropdownMenu.Root>
</nav>
