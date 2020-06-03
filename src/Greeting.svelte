<script>
	// Modules: 
	// import {time, readable} from 'svelte/store'
	
	// Variables:
	let current = new Date
	let hours = current.getHours()
	let minutes = current.getMinutes()
	let seconds = current.getSeconds()
	let greet = ''
	// $: console.log(time)

	// Functions :
	function displayCurrentTime() {
		let currentTime = [hours, minutes, seconds]
		return currentTime.join(':')
	}
	function twoDigit(value) {
		if(value < 10) {
			value = '0' + value
		}
		return value
	}

	// Async functions 
	setTimeout(() => displayCurrentTime(), 1000)

	// Reactivity :
	$: {
		if (hours < 12) greet = 'morning'
		else if (hours < 17) greet = 'afternoon'
		else greet = 'evening'
	}
	$: twoDigit(hours)
	$: twoDigit(minutes)
	// $: if(minutes.length == 1) minutes= `0${minutes}` 
</script>

<!-- <p id="clock">{displayCurrentTime()}</p> -->
<h1>Good {greet} dude!</h1>

<style>
/* #clock {  float: right;} */

h1 {
	color: purple;
	text-transform: uppercase;
	font-size: 4em;
	text-shadow: 2px -1px 2px fuchsia;
}
</style>