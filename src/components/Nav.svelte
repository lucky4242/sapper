<script>
  export let segment;
  const handleClick = () => {
    console.log(segment);
  };
</script>

<nav>
  <div>
    <h1 on:click={handleClick}>JOB FORAGE</h1>
    <ul>
      <li><a class:current={segment === undefined} href=".">Home</a></li>
      <li><a class:current={segment === "about"} href="about">About</a></li>
      <li>
        <a class:current={segment === "contact"} href="contact">Contact</a>
      </li>
      <li><a class:current={segment === "Jobs"} href="Jobs">Jobs</a></li>
    </ul>
  </div>
</nav>

<style> 
  nav {
    background: #fff3ef;
  }
  nav div {
    max-width: 960px;
    padding: 0 10px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    text-align: center;
  }
  h1 {
    margin-top: 20px;
    font-size: 30px;
    font-weight: bold;
    /* display:flex; */
    text-align: left;
  }
  ul {
    padding: 0;
    margin: 0;
    text-align: right;
  }
  li {
    display: inline-block;
  }
  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
  a.current {
    border-bottom: 3px solid #ff3e00;
  }
</style>
