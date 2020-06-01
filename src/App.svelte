<script>
	let name = ""
	let job = ""
	let image = ""
	let desc = ""
	
	// const {name, job, image, desc} = user
	let done = false
	let formState = 'empty'
	let createdContacts = []
	/* 
	*/
	import Switch from './Switch.svelte'
	import Clock from './Clock.svelte'
	import Greeting from './Greeting.svelte'
	import ContactCard from './ContactCard.svelte'

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
		createdContacts = [...createdContacts, {
			name,
			job,
			image,
			desc 
		}]
		formState = 'done'

	
	}
	// $: console.log(user.hasIndex)
	$: console.log(formState)

</script>

<svelte:head>
	<title>Svelte first app</title>
</svelte:head>

<main>
	<!-- <Clock /> -->
	<Greeting />
	
	<h2>Nice to meet you!</h2>
	
	<hr>
		<input type="text" bind:value="{name}" placeholder="name: " ><br>
		<input type="text" bind:value="{job}" placeholder="job: " ><br>
		<input type="text" bind:value="{image}" placeholder="image path: " ><br>
		<textarea bind:value="{desc}" placeholder="description"></textarea><br>
		<button on:click={addContact}>
			Add contact
			<!-- <input type="submit" value="Add Contact" > -->
		</button>
		
		
		{#if formState == 'invalid'}
		<p class="error">Invalid</p>
		{:else}
		<p class="warning">Please enter data and click the button</p>
		{/if}

		{#each createdContacts as contact, i}
		{#if createdContacts.length > 1}	
			<h2>#{i + 1}</h2>
		{/if}
		<ContactCard 
		name={contact.name} 
		job={contact.job} 
		image={contact.image} 
		desc={contact.desc}/>
		{:else}
		<p class="warning">You have to fill the form if you wanna display your card.</p>
		{/each}
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
	.error {
		color: red;
	}
	.warning {
		color: orangered;
	}

	

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>