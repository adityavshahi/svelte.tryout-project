<script>
    let name = '';
    let age = null;
    import {createEventDispatcher} from 'svelte';

    function onSubmit(e) {
        console.log("Form Submitted!!");
    }
</script>

<form on:submit|preventDefault={onSubmit}>
    <label for="name">Name: </label>
    <input type="text" bind:value={name} id="name">
    <label for="age" >Age: </label>
    <input type="number" bind:value={age} id="age">
    <button type="submit">Submit</button>
</form>