<script>
    let listItems = ["position", "length", "angle"]
</script>


<p>The best visual channels ordered by Mackinlay's ranking:</p>
<ul>
    {#each listItems as name}
      <li>{name}</li>
    {/each}
  </ul>