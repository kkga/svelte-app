<script>
  import { lastClicked } from "./stores";
  import Button from "./Button.svelte";

  function handleMessage(event) {
    lastClicked.set(event.detail.value);
  }
</script>

<main>
  <h1>{$lastClicked}</h1>
  <Button on:message={handleMessage} label="1" />
  <Button on:message={handleMessage} label="2" />
  <Button on:message={handleMessage} label="3" />

  <hr />

  {#if $lastClicked === "1"}
    <div>one</div>
  {/if}
</main>

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
