<script>
    let letter = '';
    let clickMe = (e) => {
        alert("Button was clicked !!");
    }
    function keyPressed(e) {
        letter = e.key;
    }
    function handleSubmit(e) {
        console.log('Form submitted!!');
    }
</script>

<button on:click={clickMe}>Click Me</button>
<svelte:window on:keypress={keyPressed} />
<h3>{letter}</h3>
<form on:submit|preventDefault={handleSubmit}>
    <button type="submit">Submit</button>
</form>