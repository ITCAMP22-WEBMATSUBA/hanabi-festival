

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
<p class="text-center">สุมครั้งละ 10 coin</p>
<div class="flex justify-center min-h-75">
    <div>
    {#if !yay}
    <p class="p-10 rounded-xl font-bold text-4xl h-64 flex items-center justify-center bg-green-200">
  สุ่มเลยยย!!
</p>
        {:else}
            {#if prize.length >0}
    {#if prize[index].includes(".jpg")}
    <img src="{prize[index]}" width="500" height="300" class="rounded-xl">
    {:else}
    <p class="p-10  rounded-xl font-bold text-4xl h-64 flex items-center justify-center bg-green-200">
  {prize[index]}
</p>
    {/if}
    {/if}

    {#if yay}
    <p>ยินดีด้วย! อย่าลืมไปรับของรางวัล</p>
    {/if}
    {/if}

    <button onclick={random} class="bg-black text-white px-4 
py-2 rounded-2xl w-full mt-2 hover:bg-white hover:text-black duration-300
cursor-pointer border-1">Random</button>
    </div>
</div>


