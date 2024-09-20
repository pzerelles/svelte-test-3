<script lang="ts">
	import type { Snippet } from 'svelte';

	let { children, ...props }: { children: Snippet } = $props();
</script>

<p {...props}>
	{#if children}{@render children()}{/if}
</p>
