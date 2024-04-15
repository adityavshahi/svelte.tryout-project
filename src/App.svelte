<script>
  import Child from './Child.svelte';
  import Fun from './Fun.svelte';

  let name = 'Naruto';
  let address = 'Konoha Village';
  let fontSize = '';
  setTimeout(() => {
    name = 'Sasuke';
    fontSize = '1.8em';
  },1000);

  let size = 1;
</script>

<h1>Hello World - Svelte</h1>
<Fun />
<p style="font-size: {fontSize};">Name : {name.toUpperCase()},Address: {address}</p>
<h3>SIZE : {size}</h3>
<Child bind:fontSize={size} />