

<style>
h2{
    text-align: center;
}
form{
    max-width: 360px;
    margin:40px auto;
    text-align:center;
}
input, textarea{
display:block;
width:100%;
padding:10px;
font-family:arial;
margin:10px auto;
border:1px solid #eee;
border-radius:8px;

}
</style>



<script>
    import { goto } from '@sapper/app';
    import { onMount } from 'svelte';
    import axios from 'axios'
    
    let allJob_type = [];
    let title = "";
    let salary = "";
    let Jobtype = [];
    let details = "";
    let error = null;
    
    
    async function handleSubmit() {
        try {
            const response = await axios.post("http://localhost:1337/api/Jobs", {
               data: { Name: title,
                Salary: salary,
                Experience: details,
                Job_types: Jobtype,
               },

            });
            Jobtype=response.data.data
            goto('Jobs');

        } catch(e) {
            error = e
        }
    }

    onMount(async () => {
	try {
		const response = await axios.get('http://localhost:1337/api/job-types');
		allJob_type = response.data.data
        console.log(allJob_type);
	} catch(e) {
		error = e
	}
});
    
    </script>
    
    {#if error !== null}
      {error}
    {:else}

       <h2>Add a Job </h2>
       <form>
        <input type ="text" placeholder="Job Title" bind:value={title} required >
        <input type ="number" placeholder="Amount $" bind:value={salary}  required >
        <textarea type ="text" placeholder="Job Requirement" bind:value={details}  required></textarea> 
         <br />
		Select Job_type
		<br />
		{#each allJob_type as jobtype}
			<label>{jobtype["attributes"]["name"]}</label>
		  <input type="checkbox" bind:group={Jobtype} value={jobtype} />
		{/each} 
        <input type="submit" value="Submit" on:click={handleSubmit} />
    </form>

    
    {/if}