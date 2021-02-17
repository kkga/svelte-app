<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  export let label = "button";

  function onClick() {
    dispatch("message", {
      value: label,
    });
  }
</script>

<button on:click={onClick}>{label}</button>
