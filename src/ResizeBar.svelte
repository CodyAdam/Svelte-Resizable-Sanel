<script>
  import { onMount } from "svelte";

  export let direction = "horizontal";

  let dragging = false;
  let size;
  let startPos;
  let pos = 50;

  function handleMousedown(e) {
    dragging = true;
    startPos = e.clientY;
  }
  function handleMousemove(e) {
    if (dragging) pos = (100 * e.clientY) / size;
  }
  function handleMouseup(e) {
    dragging = false;
  }
</script>

<style lang="scss">
  .container {
    width: 100%;
    height: 100%;
    display: grid;
    overflow: hidden;
  }

  .h-bar {
    background-color: greenyellow;
    height: 5px;
    width: 100%;
  }

  .v-bar {
    background-color: greenyellow;
    height: 100%;
    width: 5px;
  }
</style>

<div
  class="container"
  style="grid-template-rows: {pos}% 5px auto"
  bind:clientHeight={size}
  on:mouseleave={handleMouseup}
  on:mousemove={handleMousemove}
  on:mouseup={handleMouseup}>
  <slot name="first" />
  <div
    class={direction === 'vertical' ? 'v-bar' : 'h-bar'}
    on:mousedown={handleMousedown} />
  <slot name="second" />
</div>
