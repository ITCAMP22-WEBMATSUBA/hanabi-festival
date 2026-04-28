

<script>
    let light_color = ["#fcba03", "#009124", "#f70000"]
    let curr_light = $state(0)
</script>



<h1 class="text-center font-bold text-4xl">Click ปุ่มตามสีที่ปรากฏ</h1>

<div class="w-[400px] h-[400px]" style="background-color: {light_color[curr_light]};">
</div>


<button class="bg-black px-5 py-2 cursor-pointer text-white rounded-xl">เริ่มเลย!</button>