 <!-- -->





 <svelte:head>
  <title>Begining sapper</title>
</svelte:head>

<div>
  <img src="jet.jpg" alt="" />
  <h1>Job Nina</h1>
  <p>find your dream right here</p>
  <a href="Jobs" class="btn">View Jobs</a>
</div>

<style>
  h1,
  p {
    text-align: center;
    margin: 0 auto;
  }
  h1 {
    font-size: 2em;
    text-transform: uppercase;
    font-weight: 700;
    margin: 0 0 0 0.5em 0;
  }
  img {
    width: 200px;
    margin: 0 auto;
    display: block;
  }
  a {
    margin: 40px;
  }
  div {
    margin-top: 60px;
    text-align: center;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 4em;
    }
  }
</style> 

