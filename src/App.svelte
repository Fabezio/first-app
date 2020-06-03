<script>
	// Components: 
	import Switch from './Switch.svelte'
	import Clock from './Clock.svelte'
	import Greeting from './Greeting.svelte'
	import ContactCard from './ContactCard.svelte'

	// Variables
	let createdContacts = []
	let name = ""
	let job = ""
	let image = ""
	let desc = ""
	let id
	let primaryKey
	let done = false
	let formState = 'empty'
	
	// Functions
	function addContact() {
		if (
			name.trim().length == 0 || 
			job.trim().length == 0 || 
			image.trim().length == 0 || 
			desc.trim().length == 0
		) {
			formState = 'invalid'
			return
		} 
		primaryKey += 1
		console.log(createdContacts.lastIndexOf())
		createdContacts = [...createdContacts, {
			id: primaryKey,
			name,
			job,
			image,
			desc 
		}]
		formState = 'done'
	}
	
	// Reactivity
	// $: console.log(user.hasIndex)
	$: console.log("card # " + primaryKey)
	$: console.log(formState)
	$: if(!createdContacts.length) primaryKey = 0

</script>

<svelte:head>
	<title>Svelte Contact Cards</title>
</svelte:head>

<main>
	<!-- <Clock /> -->
	<Greeting />
	
	<h2>Leave a <span class="error">contact card</span>!</h2>
	
	<hr>
	<form>
	<input type="text" bind:value="{name}" placeholder="name: " ><br>
	<input type="text" bind:value="{job}" placeholder="job: " ><br>
	<input type="text" bind:value="{image}" placeholder="image path: " ><br>
	<textarea bind:value="{desc}" placeholder="description"></textarea><br>
	<br>
	<button class="bg-success" type="submit" on:click|preventDefault={addContact}>
		Add Contact
	</button>
	</form>
	<button class="bg-danger" on:click={event => createdContacts = createdContacts.slice(1)}>
		Remove First Contact
	</button>
	<button class="bg-warning" on:click={event => createdContacts = createdContacts.slice(0, -1)}>
		Remove Last Contact
	</button>
	
	
	{#if formState == 'invalid'}
	<p class="error">Invalid, you must complete the form.</p>
	{:else}
	<p class="warning">Please enter data and click the button</p>
	{/if}

	{#if createdContacts.length}
		{#each createdContacts as contact, i}
			{#if createdContacts.length > 1 || primaryKey > 1}	
				<h2 class="mb-0">#{ contact.id}</h2>
			{/if}
		<ContactCard 
		name={contact.name} 
		job={contact.job} 
		image={contact.image} 
		desc={contact.desc}/>
		{:else}
		<p class="warning">You have to fill the form if you wanna display your card.</p>
		{/each}
	{/if}
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
		/* background-color: hsl(0, 85%, 50%); */
		border: none;
		text-transform: uppercase;
		padding: .5em 1.5em;
		font-weight: 200;
	}

	/* colors  */
	.error {color: red;}
	.warning {color: orange;}
	.bg-success {background-color: green;	}
	.bg-warning {background-color: orange;}
	.bg-danger {background-color: red;}	

	/* gaps */
	.mb-0 {
		margin-bottom: 0;
	}
	.mb-1 {
		margin-bottom: 1em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>