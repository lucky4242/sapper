<script>
  import { onMount } from "svelte";
  import axios from "axios";

  let jobs = [];
  let error = null;
  

  const getJob = () => {
    axios.get("http://localhost:1337/api/Jobs").then((res) => {
      jobs = res.data.data;
      console.log(jobs["id"]["attributes"]["Name"]);
      console.log(jobs);
      return { jobs };
    });
  };
  onMount(getJob);
</script>
<style>
  ul{
    padding:0px;
  }
  li{
    list-style-type:none;
    padding: 10px;
   
  }
  ol li {
    font-weight: bold;
    font-size: 24px;

  }
    .btn{
    display:block;
    padding:15px;
    border:1px solid #6b3fca;
    border-radius:8px;
    background-color: #6b3fca;
    margin:10px auto;
    text-decoration:none;
    font-size: 20px;
  }
   a:hover{
    background-color:#9f43e5;
  }
  div{
    text-align:center;
  }
   ol li ul{
    display:none;
}
 ol li:hover ul{
    display: block;
}
</style>

<main>
<div>
  <h1>All Current Jobs</h1>
  <hr />
  </div>

  {#await jobs}
    loading...
  {:then jobs}
    <ol>
      {#each jobs as jobs}
        <li > {jobs["attributes"]["Name"]}
          <ul>
            <li>Salary:  ${jobs["attributes"]["Salary"]}</li>
            <li>Job Requirement:  {jobs["attributes"]["Experience"]}</li>
          </ul>
        </li>
      {/each}
    </ol>
  {:catch error}
    {error}
  {/await}

  <div>
    <a href="/Jobs/create" class="btn" >Add a Job </a>
  </div>
</main>
