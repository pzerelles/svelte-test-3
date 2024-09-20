<script lang="ts" generics="T extends Component<any, any> | SvelteComponent<any> = Paragraph">
	import type { Component, ComponentProps, Snippet, SvelteComponent } from 'svelte';
	import Paragraph from './Paragraph.svelte';

	let {
		As,
		level,
		children,
		...props
	}: { As?: T; level?: 'top' | 'sub'; children: Snippet } & Omit<ComponentProps<T>, 'As' | 'level' | 'snippet'> = $props();
</script>

{#if As && typeof As === 'function'}
	<As {...props}>
		{#if children}{@render children()}{/if}
	</As>
{:else if children}{@render children()}{/if}
