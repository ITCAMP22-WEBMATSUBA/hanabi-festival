

<script>
    import { onMount } from "svelte";
    import boxing from "$lib/assets/prize/boxing.jpg"
    import fan from "$lib/assets/prize/fan.jpg"
    import car from "$lib/assets/prize/lambo.jpg"

    let yay = $state(false)

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
        yay = true
        updateCoin()
    }


</script>


<h1 class="font-bold text-2xl text-center">Gacha</h1>
<p class="text-center text-blue-400">สุมครั้งละ 10 coin</p>
<div>
    {#if prize.length >0}
    {#if prize[index].includes(".jpg")}
    <img src="{prize[index]}" width="500">
    {:else}
    <p>{prize[index]}</p>
    {/if}
    {/if}

    {#if yay}
    <p>ยินดีด้วย! อย่าลืมไปรับของรางวัล</p>
    {/if}
</div>


<button onclick={random}>Random</button>