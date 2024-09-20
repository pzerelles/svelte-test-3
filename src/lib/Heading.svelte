<script lang="ts">
	import type { Snippet } from 'svelte';

	let { level, children, ...props }: { level?: 1 | 2 | 3 | 4 | 5 | 6; children?: Snippet } = $props();

	const tag = $derived(`h${level}`);
</script>

<svelte:element this={tag} {...props}>
	{#if children}{@render children()}{/if}
</svelte:element>
