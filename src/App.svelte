<script>
  import { Router, Link, Route } from 'svelte-routing';
  
  import Home from "./Routes/Home.svelte";
  import Callback from "./Routes/Callback.svelte";

  export let url = "";
</script>

<Router url="{url}">
  <nav>
    <Link to="/">Home</Link>
    <Link to="callback">Callback</Link>
  </nav>
  <div>
    <Route path="/"><Home /></Route>
    <Route path="/callback" component="{Callback}" />

  </div>
</Router>