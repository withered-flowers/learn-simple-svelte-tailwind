<script setup>
  import ThirdComponentSubTableContent from "./ThirdComponentSubTableContent.svelte";

  export let extData;
</script>

<table class="table-auto">
  <thead>
    <tr>
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
      <th>avatar</th>
    </tr>
  </thead>
  <tbody>
    <!-- Create the loop for rendering the data  -->
    <!-- Loop the table rows and pass the item -->
    <!-- note that (item.id) is the key (keyed each blocks svelte) -->
    {#each extData as item (item.id)}
      <ThirdComponentSubTableContent {item} />
    {/each}
  </tbody>
</table>

<style></style>
