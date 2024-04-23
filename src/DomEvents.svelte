<script>
    let letter = '';
    let clickMe = (e) => {
        alert("Button was clicked !!");
    }
    function keyPressed(e) {
        letter = e.key;
    }
</script>

<button on:click={clickMe}>Click Me</button>
<svelte:window on:keypress={keyPressed} />
<h3>{letter}</h3>