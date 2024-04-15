<script>
    export let fontSize = 1;

    setInterval(() => {
        if(fontSize < 10 || fontSize === 1) {
            fontSize++;
        } else {
            fontSize = 1;
        }
    },100)
</script>

<h3 style="font-size: {fontSize}em;">Child Component</h3>