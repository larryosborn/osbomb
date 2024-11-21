<script lang="ts">
	import { Github, Twitter, Linkedin } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button';
	import * as Card from '$lib/components/ui/card';

	const links: string[] = [
		'https://github.com/larryosborn',
		'https://twitter.com/limefest',
		'https://www.linkedin.com/in/larryosborn/',
		'https://bsky.app/profile/osbomb.com'
	];
</script>

<Card.Root>
	<Card.Header class="space-y-1">
		<Card.Title class="text-2xl">osbomb dot com</Card.Title>
		<Card.Description>Hi, I'm Larry Osborn.</Card.Description>
	</Card.Header>
	<Card.Content class="grid gap-4">
		<div class="grid grid-cols-4 gap-4">
			{#each links as href}
				{@render link(href)}
			{/each}
		</div>
	</Card.Content>
</Card.Root>

{#snippet icon(href: string)}
	{#if href.startsWith('https://github.com/')}
		<Github class="h-4 w-4" />
	{:else if href.startsWith('https://twitter.com/')}
		<Twitter class="h-4 w-4" />
	{:else if href.startsWith('https://www.linkedin.com/')}
		<Linkedin class="h-4 w-4" />
	{:else if href.startsWith('https://bsky.app/')}
		<div class="h-4 w-4">
			<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 568 500.13">
				<path
					fill="currentColor"
					d="M123.121 33.664C188.241 82.553 258.281 181.68 284 234.873c25.719-53.192 95.759-152.32 160.879-201.21C491.866-1.611 568-28.906 568 57.947c0 17.346-9.945 145.713-15.778 166.555-20.275 72.453-94.155 90.933-159.875 79.748 114.875 19.55 144.097 84.31 80.986 149.07-119.86 122.992-172.272-30.859-185.702-70.281-2.462-7.227-3.614-10.608-3.631-7.733-.017-2.875-1.169.506-3.631 7.733-13.43 39.422-65.842 193.273-185.702 70.281-63.111-64.76-33.89-129.52 80.986-149.071-65.72 11.185-139.6-7.295-159.875-79.748C9.945 203.659 0 75.291 0 57.946 0-28.906 76.135-1.612 123.121 33.664Z"
				/>
			</svg>
		</div>
	{/if}
{/snippet}

{#snippet link(href: string)}
	<Button variant="outline" class="text-primary" {href} target="_blank">
		{@render icon(href)}
	</Button>
{/snippet}
