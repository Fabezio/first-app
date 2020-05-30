<script>
export let user
</script>

<div class="card">
  <h1>
  My contact card
  </h1>
  <p class="name">name: {user.name}</p>
  <p class="job">job: {user.job}</p>
  <p class="desc">description:
  <br><span class="desc-content">{user.desc}</span></p>
  <p class="job">contact: {user.email}</p>

</div>

<style>
.card {
  width: 600px;
  height: 300px;
  border: 2px ridge #777;
  border-radius: 3px;
  box-shadow: 10px 10px 10px #777;
  margin: 2.5em auto;
  padding: 0.5em 1em;
}
.name, .job, .desc {
  color: black;
  text-align: left;
  
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
  
.desc-content {
  padding-left: 1.5em;
  text-align: justify;
  font-size: 0.9em;
}

</style>