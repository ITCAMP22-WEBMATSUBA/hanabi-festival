

<script>
    import { onMount } from "svelte";
    import boxing from "$lib/assets/prize/boxing.jpg"
    import fan from "$lib/assets/prize/fan.jpg"
    import car from "$lib/assets/prize/lambo.jpg"

    let coins = 0;
    onMount(()=>{
        coins = JSON.parse(localStorage.getItem('coins')) || 0;
    })
    let index = $state(0)
    let prize = [car, fan, boxing, "Cash 5000 Baht", "Discount 2500 Baht"]

    let cost = 10
    const updateCoin = ()=>{
        coins -= cost;
        if (coins < 0) coins = 0;
        localStorage.setItem('coins', coins);
    }

    const random = ()=>{
        let rng = Math.floor(Math.random() * prize.length);
        index = rng

        updateCoin()
    }


</script>


<h1>Gacha</h1>
<p>สุมครั้งละ 10 coin</p>
<div>
    {#if prize.length >0}
    {prize[index]}
    {/if}
</div>


<button onclick={random}>Random</button>