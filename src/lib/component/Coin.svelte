<script>
    import { onMount } from "svelte";

    let {coins = $bindable(0)} = $props();
    let coin = $state(0);
    onMount(()=>{
        coin = parseInt(localStorage.getItem("coins")) || 0;
    })
</script>

<p class="h-10 bg-">Coin: {coin}</p>


