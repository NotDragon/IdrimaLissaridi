<script lang="ts">
	import favicon from '#lib/assets/favicon.svg';
	import DesignToggle from '#lib/DesignToggle.svelte';
	import type { LayoutProps } from './$types';

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
<DesignToggle />
