<script>
  // We will create a child component to hold the content
  import SecondComponentSubContent from "./SecondComponentSubContent.svelte";

  // state for the text
  let textInput = "";
</script>

<div>
  <h2 class="h2">Second Component</h2>
  <div class="custom-subcontainer">
    <!-- Form Section -->
    <section class="mr-4">
      <form>
        <!-- Two way data binding automatically using bind:value -->
        <input
          class="form-input"
          type="text"
          placeholder="Write me pl0x"
          bind:value={textInput}
        />
      </form>
    </section>
    <section>
      <!-- Content section  -->

      <!-- pass textInput to SecondComponentSubContent -->
      <SecondComponentSubContent {textInput} />
    </section>
  </div>
</div>

<style></style>
