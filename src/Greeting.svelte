<script>
let hours = new Date().getHours()
let minutes = new Date().getMinutes()
let greet = ''
function twoDigit (value) {
	if(value.length == 1) {
		value = `0${value}`
		}
}

$: {
  if (hours < 12) greet = 'morning'
  else if (hours < 17) greet = 'afternoon'
  else greet = 'evening'
}
$: twoDigit(hours)
$: twoDigit(minutes)
// $: if(minutes.length == 1) minutes= `0${minutes}` 
</script>

<p id="clock">{hours}:{minutes}</p>
<h1>Good {greet} dude!</h1>
<style>
#clock {
  float: right;
}

h1 {
	color: purple;
	text-transform: uppercase;
	font-size: 4em;
	text-shadow: 2px -1px 2px fuchsia;
}
</style>