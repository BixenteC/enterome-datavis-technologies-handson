<style>
  .currentSelection {
    background-color: blue;
  }
</style>

<script>
  let current = "";
</script>

<!-- We will cover buttons later on! -->
<button class="btn btn-secondary" class:currentSelection={current == "messi"} on:click={() => (current = "messi")}>
  Messi
</button>

<button class="btn btn-secondary" class:currentSelection={current == "ronaldo"} on:click={() => (current = "ronaldo")}>
  Ronaldo
</button>

<button class="btn btn-secondary" class:currentSelection={current == "neymar"} on:click={() => (current = "neymar")}>
  Neymar
</button>
