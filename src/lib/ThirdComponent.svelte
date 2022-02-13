<script>
  import { onMount, onDestroy } from "svelte";
  import ThirdComponentSubTable from "./ThirdComponentSubTable.svelte";

  let extData = [];

  const fetchData = async () => {
    // fetch data from external API
    const response = await fetch("https://reqres.in/api/users");
    const jsonData = await response.json();

    // set fetched data to state
    extData = [...extData, ...jsonData.data.slice(0, 3)];
  };

  // we will fetch the data from the external API
  // using the methods that we have created
  // the fetchExternalData method

  // this is the same as componentDidMount on React
  onMount(() => {
    fetchData();
  });

  // this is the same as componentDidUnmount on React
  onDestroy(() => {});
</script>

<div>
  <h2 class="h2">Third Component</h2>
  <ThirdComponentSubTable {extData} />
</div>

<style></style>
