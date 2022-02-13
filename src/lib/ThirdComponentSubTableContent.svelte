<script>
  export let item;
</script>

<tr>
  <td>{item.first_name}</td>
  <td>{item.last_name}</td>
  <td>{item.email}</td>
  <td>
    <img src={item.avatar} alt={item.avatar} />
  </td>
</tr>

<style></style>
