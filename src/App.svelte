<script>
	export let name;
	export let age;
	let job = ""
	let email = ""
	let desc = ""
	let user = {
		name,
		job, 
		email, 
		desc
	}
	/* 
	*/
	import Switch from './Switch.svelte'
	import Greeting from './Greeting.svelte'
	import ContactCard from './ContactCard.svelte'
	// import Compo from './Compo.svelte'
	$: nameUppercase = user.name.toUpperCase()
	$: console.log(`age: ${age}`)
	$: console.log(`name: ${name}`)
	// $: console.log(`job: ${job}`)
	$: if (name === 'Valiant Coder') age = 22
	

	function incrementAge () {
		age += 1
	}
	function changeName () {
		user.name = "Valiant Coder"
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
	<button on:click={changeName}>Change Name</button><br>
	<input type="text" bind:value="{user.name}" placeholder="name: " ><br>
	<input type="text" bind:value="{user.job}" placeholder="job: " ><br>
	<input type="email" bind:value="{user.email}" placeholder="email: " ><br>
	<textarea bind:value="{user.desc}" placeholder="description"></textarea><br>
	<ContactCard {user}/>
<!--

<Switch />
-->	
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