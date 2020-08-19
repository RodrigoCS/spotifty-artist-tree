<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();
  function handleClick (e) {
    e.preventDefault();
    e.stopPropagation();
    dispatch('click')
  }
</script>

<button on:click={handleClick}>
  <slot>Button</slot>
</button>
