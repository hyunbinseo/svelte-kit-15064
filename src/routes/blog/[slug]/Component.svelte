<script lang="ts">
	import type { Snippet } from 'svelte';
	import { SvelteDate } from 'svelte/reactivity';

	const { snippet }: { snippet: Snippet<[{ now: number }]> } = $props();

	const date = new SvelteDate();

	$effect(() => {
		const interval = setInterval(() => {
			date.setTime(Date.now());
		}, 1000);

		return () => {
			clearInterval(interval);
		};
	});

	$inspect(date.valueOf());
</script>

{@render snippet({ now: date.getTime() })}
