<script>
	import "../main.css"

	import favicon from '$lib/assets/favicon.svg';
	import Coin from '$lib/component/Coin.svelte';
	let { children } = $props();

</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<Coin />
{@render children()}
