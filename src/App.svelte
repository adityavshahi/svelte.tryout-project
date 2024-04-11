<script>
  import Fun from './Fun.svelte';

  let name = 'Naruto';
  let address = 'Konoha Village';
  let fontSize = '';
  setTimeout(() => {
    name = 'Sasuke';
    fontSize = '1.8em';
  },1000)
</script>

<h1>Hello World - Svelte</h1>
<Fun />
<p style="font-size: {fontSize};">Name : {name.toUpperCase()},Address: {address}</p>