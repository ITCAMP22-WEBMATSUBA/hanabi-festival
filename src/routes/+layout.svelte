<script>
	import favicon from '$lib/assets/favicon.svg';
	import Coin from '$lib/component/Coin.svelte';
	let { children } = $props();
	let coins = 10;
</script>

<Coin coins={coins}/>
<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
