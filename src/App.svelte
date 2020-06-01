<script>
	let user = {
		name: "",
		job: "", 
		image: "", 
		desc: ""
	}
	let done = false
	/* 
	*/
	import Switch from './Switch.svelte'
	import Greeting from './Greeting.svelte'
	import ContactCard from './ContactCard.svelte'

	function addContact() {
		done = true

	}
	
	// $: console.log(user.hasIndex)
	$: console.log(done)

</script>

<svelte:head>
	<title>Svelte first app</title>
</svelte:head>

<main>
	<Greeting />
	
	<h2>Nice to meet you!</h2>
	
	<hr>
		<input type="text" bind:value="{user.name}" placeholder="name: " ><br>
		<input type="text" bind:value="{user.job}" placeholder="job: " ><br>
		<input type="text" bind:value="{user.image}" placeholder="image path: " ><br>
		<textarea bind:value="{user.desc}" placeholder="description"></textarea><br>
		<button on:click={addContact}>
			Add Contact
			<!-- <input type="submit" value="Add Contact" > -->
		</button>
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