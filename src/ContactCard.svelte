<script>
export let name
export let job
export let desc
export let image
</script>

<div class="card">
  <h1>My contact card</h1>
  <div class="row" >
    <div class="col">
      <figure>
        <div class={image ? '' : 'frame'}>
          <img src={image} alt={name}>
        </div>
      </figure>
    </div>
    <div class="col">
      <p id="name">
        <span class={name? 'line-text' : 'text-muted'}>{name}</span>
      </p>
        
      <p id="job">
        <span class={job? 'line-text' : 'text-muted'}>{job}</span>
      </p>
    </div>
  </div>
  <hr>
  <p id="desc">
    <span class={desc? 'line-text' : 'text-muted'}>{@html desc}</span>
  </p>

</div>

<style>
.row {display: flex;}
.col {display: block;}

.frame {
  border-radius: 1em;
  border: solid 1px rgba(0,0,0, .1);
  background: grey;
}
img {
  width: 100px;
  min-height: 100px;
}

.card {
  width: 400px;
  min-height: 225px;
  border: 2px ridge #777;
  border-radius: 3px;
  box-shadow: 10px 10px 10px #777;
  margin: 2.5em auto;
  padding: 0.5em 1em;
}
.card:hover {transform: translate(0, 2px);}
#name, 
#job, 
#desc {
  color: black;
  text-align: left;
}
  
/* #desc-content {
  padding-left: 1.5em;
  text-align: justify;
  font-size: 0.9em;
} */
/* #contact {
  text-decoration: underline;
  font-style: oblique;
} */
/* .line-title {font-weight: 400;} */
.line-text {font-weight: 300;}

.text-muted {
  color: rgba(0,0,0,.75);
  font-size: 1em;
  font-style: oblique;
  background: rgba(0,0,0,.1);
  padding: 0.25em 0.75em 0.25em 0.25em;
  border-radius: 3px;
}

</style>