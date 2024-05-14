<script>
    let colorName = "Blue";
</script>

{#if colorName.toLowerCase() === "blue"}
    <h2>Blue</h2>
{:else if colorName.toLowerCase() === "red"}
    <h2>Red</h2>
{:else}
    <h2>Some other Color</h2>
{/if}

<input type="text" bind:value={colorName} />
<h2>{colorName}</h2>