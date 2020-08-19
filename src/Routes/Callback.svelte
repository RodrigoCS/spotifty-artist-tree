<script>
	import queryString from 'query-string';
	import { onMount } from 'svelte';

	onMount(() => {
		console.log('the component has mounted');
		const parsed = queryString.parse(location.search);
		console.log(parsed);
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

<main>
  Logged in
</main>
