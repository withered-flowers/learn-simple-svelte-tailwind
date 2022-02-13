<script>
  // get a props from parent component named 'textInput'
  // via export keywords
  export let textInput;
</script>

<div>
  {#if textInput === ""}
    <pre>I have nothing to show</pre>
  {:else}
    <pre>I write: {textInput}</pre>
  {/if}
</div>

<style></style>
