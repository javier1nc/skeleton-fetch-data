<script>
  import { onMount } from "svelte";
  const endpoint = "https://jsonplaceholder.typicode.com/posts";
  let posts = [];

  onMount(async function () {
    const response = await fetch(endpoint);
    const data = await response.json();
    console.log(data);
  
  	posts = data; //
  });

  export let name;

	
</script>

<main>
  <h1>Hello {name}!</h1>
  <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

  {#each posts as article}
    <div>
      <p>{article.title}</p>
    </div>
  {/each}
</main>


<style>
  /* ommitted for brevity */
</style>
