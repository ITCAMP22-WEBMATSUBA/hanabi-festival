<script>
	import "../main.css"

	import favicon from '$lib/assets/favicon.svg';
	import Coin from '$lib/component/Coin.svelte';
	let { children } = $props();
	let coins = 10;
	import "../app.css";
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<Coin />
{@render children()}
