<script>
    let red = 0;
    let green = 0;
    let blue = 0;

    $: colorValue = `${red}, ${green}, ${blue}`;

    setTimeout(() => {
        red += 10;
        green += 10;
        blue += 100;
    },3000);
</script>


<h2>Color : {colorValue}</h2>


