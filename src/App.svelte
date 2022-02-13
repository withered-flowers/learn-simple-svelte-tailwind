<script>
  // import the component here
  import FirstComponent from "./lib/FirstComponent.svelte";
  // import the second component here
  import SecondComponent from "./lib/SecondComponent.svelte";
</script>

<div class="custom-container bg-slate-200">
  <p class="h1">Simple Svelte Apps with Tailwind</p>
  <!-- Create new section to hold FirstComponent -->
  <section>
    <FirstComponent />
  </section>
  <!-- Create new section to hold SecondComponent -->
  <section>
    <SecondComponent />
  </section>
</div>

<style></style>
