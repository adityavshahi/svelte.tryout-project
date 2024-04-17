<script>
    export let fontSize;
</script>



<input type="range" bind:value={fontSize} max="200" min="10">
<h2 style="font-size: {fontSize}px;">Font Size : {fontSize}px</h2>