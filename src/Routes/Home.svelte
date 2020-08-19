<script>
	import Button from '../Components/Button.svelte';
	import queryString from 'query-string';
  import { onMount } from 'svelte';
  let queryParams = null;

  const handleClick = () => {
    const clientId = '373513fdefcd433b9e727091b2cdbade';
    const redirectURI = 'http://localhost:5000/';
    const state = '123';
		const responseType = 'token';
		const scope = 'user-read-private';
		const authURL = `https://accounts.spotify.com/authorize?client_id=${clientId}&redirect_uri=${redirectURI}&scope=${scope}&response_type=${responseType}&state=${state}`;
		console.log('authURL', authURL)
    window.location.replace(authURL);
	};
  
	onMount(() => {
    const params = (location.hash);
    queryParams = queryString.parse(params);
	});
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em; 
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
{@debug queryParams}
<main>
  {#if !queryParams?.access_token}
    <Button on:click={handleClick}>Login to spotify</Button>
  {/if}
  {JSON.stringify(queryParams)}
</main>
