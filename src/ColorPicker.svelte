<script>
    let red = 0;
    let blue = 0;
    let green = 0;
</script>


<style>
    div {
        height: 20rem;
        width: 20rem;
        border: 2px solid black;
        border-radius: 0.2rem;
    }
</style>
<h1 id="colorpicker-h1">Color Picker</h1>
<h3>Red ({red})</h3>
<input type="range" bind:value={red} max="255" min="0">

<h3>Blue ({blue})</h3>
<input type="range" bind:value={blue} max="255" min="0">

<h3>Green ({green})</h3>
<input type="range" bind:value={green} max="255" min="0">


<div style="background-color: rgb({red}, {green}, {blue});"></div>