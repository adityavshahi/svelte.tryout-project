<script>
    let colorList = ['red','yellow','orange','blue']
    setTimeout(() => {
        colorList = [...colorList,'brown'];
    },3000);

    let colorValue = '';

    function addColor() {
        colorList = [...colorList,colorValue];
        colorValue = '';
    }
</script>

<hr />
<input bind:value={colorValue} type="text">
<button on:click={addColor}>Submit</button>

<ul>
    {#each colorList as color}
        <li>{color}</li>
    {/each}
</ul>