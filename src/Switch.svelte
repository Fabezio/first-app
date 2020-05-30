<script>
let switchOn = false

function toggle() {
  switchOn = !switchOn
  
}
$: console.log(`on : ${switchOn}` )
</script>
<div class="shape {switchOn? 'blue' : 'grey'}" on:click={toggle} >
  <div class="switch {switchOn? 'on ': 'off'}" ></div>
</div>
<style>
.shape {
  width: 2em;
  height: 1em;
  /* background: #c000ff; */
  border-radius: .5em;
  border: -1px inset #333;
}
.switch {
  width: 0.9em;
  height: .9em;
  /* float: left; */
  background: #cfcfff;
  border-radius: 50%;
  box-shadow: 4px 3px 5px grey;
  border: .05em inset #333;
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