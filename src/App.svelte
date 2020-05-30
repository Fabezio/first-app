<script>
	export let name;
	export let age;
	import Switch from './Switch.svelte'
	import Greeting from './Greeting.svelte'
	// import Compo from './Compo.svelte'
	$: nameUppercase = name.toUpperCase()
	$: console.log(`name: ${name}`)
	$: console.log(`age: ${age}`)

	function incrementAge () {
		age += 1
	}
	function changeName () {
		name = "Valiant Coder"
	}
</script>

<svelte:head>
	<title>Svelte first app</title>
</svelte:head>

<main>
	<Greeting />
	
	<p>Nice to meet you!</p>
	<p>I'm {nameUppercase} and {age} years old. (yea i know i dont seem)</p>
	<hr>
	<button on:click={incrementAge}>increment age</button>
	<button on:click={changeName}>Change Name</button>
	<Switch />
</main>

<style>

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	
	button {
		border-radius: 8px;
		font-size: 1.25em;
		color: white;
		background-color: hsl(0, 85%, 50%);
		border: none;
		text-transform: uppercase;
		padding: .5em 1.5em;
		font-weight: 200;
	}

	

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>