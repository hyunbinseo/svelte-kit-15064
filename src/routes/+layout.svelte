<script lang="ts">
	import { resolve } from '$app/paths';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();

	const href = resolve('/blog/lorem');
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<ol>
	<li><a {href}>Preload Enabled</a> - Reactivity Breaks</li>
	<li><a href={resolve('/')} data-sveltekit-reload>Home</a> - Full Page Navigation</li>
	<li><a {href} data-sveltekit-preload-data="off">Preload Disabled</a></li>
</ol>

{@render children()}
