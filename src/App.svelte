<script>
  import Child from './Child.svelte';
  import Fun from './Fun.svelte';
  import StyleTest from './StyleTest.svelte';
  import Slider from './Slider.svelte';
  import ColorPicker from './ColorPicker.svelte';
  import Jokes from './Jokes.svelte';
  import DomEvents from './DomEvents.svelte';
  import Form from './Form.svelte';

  let name = 'Naruto';
  let address = 'Konoha Village';
  let disabled = true;
  let fontSize = '';
  // let sliderSize = 20;
  setTimeout(() => {
    name = 'Sasuke';
    fontSize = '1.8em';
  },1000);

  let size = 1;
  let joke = 'Loading...';
  let fetchJoke = () => {
    fetch('https://api.chucknorris.io/jokes/random')
    .then(res => res.json())
    .then((data) => {
      joke = data.value;
    })
    .catch((err) => console.log(`Something Went Wrong : ${err}`));
  }
  fetchJoke()

  function onFormSubmit(e) {
    console.log(e);
    const {name,age} = e.detail;
    console.log(name,age,'details from event');
  }
</script>

<h1>Hello World - Svelte</h1>
<input type="text" bind:value={name}>
<button disabled={disabled}>Click Me</button>
<Slider fontSize={20} />
<Fun />
<p style="font-size: {fontSize};">Name : {name.toUpperCase()},Address: {address}</p>
<h3>SIZE : {size}</h3>
<!-- <Child bind:fontSize={size} /> -->
<StyleTest />


<ColorPicker />

<Jokes joke={joke}/>

<DomEvents />

<Form on:submit={onFormSubmit} />