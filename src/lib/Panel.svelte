<script lang="ts" generics="T extends Component<any, any> | SvelteComponent<any> = Paragraph">
	import type { Component, ComponentProps, Snippet, SvelteComponent } from 'svelte';
	import Paragraph from './Paragraph.svelte';

	let {
		As,
		size,
		children,
		...props
	}: { As?: T; size?: 'sm' | 'md' | 'lg' | 'xl'; children: Snippet } & Omit<ComponentProps<T>, 'As' | 'size' | 'children'> = $props();
</script>

{#if As && typeof As === 'function'}
	<As {...props}>
		{#if children}{@render children()}{/if}
	</As>
{:else if children}{@render children()}{/if}
