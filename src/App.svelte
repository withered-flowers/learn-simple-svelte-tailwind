<script>
  // import the component here
  import FirstComponent from "./lib/FirstComponent.svelte";
  // import the second component here
  import SecondComponent from "./lib/SecondComponent.svelte";
  // import the third component here
  import ThirdComponent from "./lib/ThirdComponent.svelte";
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
  <!-- Create new section to hold ThirdComponent -->
  <section>
    <ThirdComponent />
  </section>
</div>

<style></style>
