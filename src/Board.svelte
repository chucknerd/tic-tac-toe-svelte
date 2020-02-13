<script>
  import Square from "./Square.svelte";
  let squares = [null, null, null, null, null, null, null, null, null];

  let xIsNext = true;
  $: status = "Next PLayer: " + (xIsNext ? "X" : "O");

  function handleClick(i) {
    if (!squares[i]) {
      squares[i] = isNext ? "X" : "O";
      xIsNext = !xIsNext;
    }
  }
</script>

<style>
  .board {
    display: flex;
    flex-wrap: wrap;
    width: 300px;
  }
</style>

<div class="board">
  {#each squares as square, i}
    <Square value={i} />
  {/each}
</div>
