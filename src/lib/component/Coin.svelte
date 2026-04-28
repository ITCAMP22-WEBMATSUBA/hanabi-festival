<script>
    import { onMount } from "svelte";

    let {coins = $bindable()} = $props()
    onMount(()=>{
        coins = JSON.parse(localStorage.getItem('coins'))
    })
</script>

<p>Coin: {coins}</p>


