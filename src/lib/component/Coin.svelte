<script>
  import { onMount } from "svelte";

  let { coins = $bindable(0) } = $props();
  let coin = $state(0);
  onMount(() => {
    coin = parseInt(localStorage.getItem("coins")) || 0;
  });
</script>

<div class="flex items-center justify-center bg-pink-300">
  <div class="container px-4">
    <p >Coin: {coin}</p>
  </div>
</div>
