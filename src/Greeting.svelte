<script>
let hours = new Date().getHours()
let minutes = new Date().getMinutes()
let greet = ''
$: {
  if (hours < 12) greet = 'good morning'
  else if (hours < 17) greet = 'good afternoon'
  else greet = 'good evening'
}
</script>

<p id="clock">{hours}:{minutes}</p>
<h1>{greet} dude!</h1>
<style>
#clock {
  float: right;
}

h1 {
		color: purple;
		text-transform: uppercase;
		font-size: 4em;
		text-shadow: 2px -1px 2px fuchsia;
		
		/* font-weight: bold; */
	}
</style>