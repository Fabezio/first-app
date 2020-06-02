
<script>
  const date =  new Date
  // let dateNow = date.now()
  const options = {
    // weekday: "long",
		// year: "numeric",
		// month: "long",
		// day: "numeric", 
		hour12: false,
		hour: "2-digit",
		minute: "2-digit",
		second: "2-digit"
	}
  const formatter = new Intl.DateTimeFormat("en-US", options)

  // $: setTimeout(refresh(date), 1000)
</script>

<!-- <p>Clock template</p> -->
<p id="clock">{formatter.format(date)}</p>

<style>
#clock {float: right;}
</style>