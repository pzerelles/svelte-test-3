<script lang="ts">
	import Title from './Title.svelte';
	import Panel from './Panel.svelte';
	import Heading from './Heading.svelte';
	import type { ComponentProps } from 'svelte';

	let title1: Expand<ComponentProps<Title>>;
	let title2: Expand<ComponentProps<Title<Panel>>>;
	let title3: Expand<ComponentProps<Title<typeof Panel>>>;
</script>

<Title level={7}>Hello, World!</Title>

<Title As={Panel} size="xxl" level={7}>Hello, World!</Title>

<Panel size="xxl">Panel</Panel>

<Panel As={Title} size="xxl" level={7}>Panel</Panel>

<Panel As={Heading} size="xxl" level={7}>Panel</Panel>
