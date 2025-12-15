<script>
	import Component from './Component.svelte';
</script>

<Component>
	{#snippet snippet({ now })}
		{now}
	{/snippet}
</Component>
