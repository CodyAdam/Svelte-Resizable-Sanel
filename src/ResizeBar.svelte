<script lang="typescript">
  export let isVertical: boolean = true;
  export let max: number = 90;
  export let min: number = 10;
  export let thickness: number = 5;
  export let pos: number = 50;

  let div: HTMLElement;
  let dragging: boolean = false;
  let size: number;
  let startPos: number;

  function handleMousedown(e) {
    dragging = true;
    updateSize();
    startPos = isVertical ? e.clientX : e.clientY;
  }

  function handleMousemove(e) {
    if (dragging) {
      console.log(size);
      pos = (100 * (isVertical ? e.clientX : e.clientY)) / size;
      pos = Math.min(Math.max(pos, min), max);
    }
  }

  function handleMouseup(e) {
    dragging = false;
  }

  function updateSize() {
    size = isVertical ? div.clientWidth : div.clientHeight;
  }
</script>

<style type="text/scss">
  .container {
    width: 100%;
    height: 100%;
    display: grid;
    overflow: hidden;
  }

  .h-bar {
    background-color: #8bca67;
    &:hover {
      cursor: ns-resize;
    }
  }

  .v-bar {
    background-color: #8bca67;
    &:hover {
      cursor: ew-resize;
    }
  }
</style>

<div
  bind:this={div}
  class="container"
  style="grid-template-{isVertical ? 'columns' : 'rows'}: {pos}% {thickness}px
  auto; cursor : {dragging ? (isVertical ? 'ew-resize' : 'ns-resize') : ''}"
  on:mousemove={handleMousemove}
  on:mouseup={handleMouseup}>
  <slot name="1" />
  <div class={isVertical ? 'v-bar' : 'h-bar'} on:mousedown={handleMousedown} />
  <slot name="2" />
</div>
