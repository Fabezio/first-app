<script>
let switchOn = false

function toggle() {
  switchOn = !switchOn
  
}
$: console.log(`switch is ${switchOn ? 'on' : 'off'}` )
</script>
<div class="shape {switchOn? 'blue' : 'grey'}" on:click={toggle} >
  <div class="switch {switchOn? 'on ': 'off'}" ></div>
</div>
<style>
.shape {
  width: 2em;
  height: 1em;
  border-radius: .5em;
  border: -1px inset #333;
}
.switch {
  width: 0.9em;
  height: .9em;
  background: #cfcfff;
  border-radius: 50%;
  box-shadow: 4px 3px 5px grey;
  border: .07em dotted #333;
}
.grey {
  background-color: grey;
}
.blue {
  background-color: deepskyblue;
}
.off {
  float: left;
}
.on {
  float: right;
}
</style>