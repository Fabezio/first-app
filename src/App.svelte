<script>
	export let name;
	export let age;
	import Switch from './Switch.svelte'
	// import Compo from './Compo.svelte'
	function incrementAge () {
		age += 1
	}
</script>

<main>
	<h1>Hello Dude!</h1>
	<p>Nice to meet you!</p>
	<p>I'm {name} and {age} years old. (yea i know i dont seem)</p>
	<hr>
	<button on:click={incrementAge}>increment age</button>
	<Switch />
</main>

<style>

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: purple;
		text-transform: uppercase;
		font-size: 4em;
		text-shadow: 2px -1px 2px fuchsia;
		
		/* font-weight: bold; */
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