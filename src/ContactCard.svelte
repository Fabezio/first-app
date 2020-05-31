<script>
export let user
</script>

<div class="card">
  <h1>My contact card</h1>
  <div class="row" >
    <div class="col">
      <figure>
        <div class={user.image ? '' : 'frame'}>
          <img src={user.image} alt= {user.name}>
        </div>
      </figure>
    </div>
    <div class="col">
      <p id="name">
        <!-- <span class="line-title">name: </span> -->
        <span class={user.name? 'line-text' : 'text-muted'}>{user.name || 'name'}</span></p>
        <!-- <span class='text-muted' class:line-text={user.name}>{user.name || 'name'}</span></p> -->
      <p id="job">
        <!-- <span class="line-title">job: </span> -->
        <span class={user.job? 'line-text' : 'text-muted'}>{user.job || 'job'}</span>
      </p>
    </div>
  </div>
  <hr>
  <p id="desc">
    <!-- <span class="line-title">description: </span><br> -->
    <!-- <span class="line-text desc-content">{user.desc}</span> -->
    <span class={user.desc? 'line-text' : 'text-muted'}>{@html user.desc || 'description'}</span>
  </p>
  <!-- <p id="contact">
    <span class="line-title">contact: </span>
    <span class="line-text">{user.email || 'email'}</span>
  </p> -->

</div>

<style>
.row {
  display: flex;
}
.col {
  display: block;
}
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
.card:hover {
  transform: translate(0, 2px);
}
#name, 
#job, 
#desc, 
#contact {
  color: black;
  text-align: left;
}
  
#desc-content {
  padding-left: 1.5em;
  text-align: justify;
  font-size: 0.9em;
}
#contact {
  text-decoration: underline;
  font-style: oblique;
}
.line-title {
  font-weight: 400;
}
.line-text {
  font-weight: 300;
}

.text-muted {
  color: rgba(0,0,0,.75);
  font-size: 1em;
  font-style: oblique;
  background: rgba(0,0,0,.1);
  padding: 0.25em 0.75em 0.25em 0.25em;
  border-radius: 3px;
}
/*
.job {
  color: black;
  text-align: left;
}

.desc {
  color: black;
  text-align: left;
}
*/
  

</style>