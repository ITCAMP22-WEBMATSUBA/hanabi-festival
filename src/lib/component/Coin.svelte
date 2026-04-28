<script>
    import { onMount } from "svelte";

    let {coins = $bindable(0)} = $props();
    let coin = 0;
    onMount(()=>{
        coin = JSON.parse(localStorage.getItem("coins")) || 0;
    })
</script>

<p>Coin: {0}</p>


