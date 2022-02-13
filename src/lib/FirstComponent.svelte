<script>
  // every value declare will be reactive in svelte
  // svelte reactivity is by assignments
  let count = 0;

  // method for set count state
  const addCount = () => {
    count++;
  };

  // method for reset count state
  const resetCount = () => {
    count = 0;
  };
</script>

<div>
  <h2 class="h2">First Component</h2>
  <h3>
    <!-- conditional rendering -->
    {#if count === 0}
      Don't you dare to click me !
    {:else}
      How dare you click me {count} time{count > 1 ? "s" : ""}
    {/if}
  </h3>
  <p>
    <!-- bind event on click with addCount -->
    <button class="btn" on:click={addCount}>Dare-to-click</button>
  </p>
  <p>
    <!-- bind event on click with resetCount -->
    <button class="btn" on:click={resetCount}>Forget-me-not</button>
  </p>
</div>
