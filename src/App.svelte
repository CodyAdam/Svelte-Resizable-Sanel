<script>
  import ResizeBar from "./ResizeBar.svelte";
</script>

<ResizeBar isVertical={true} pos={66}>
  <div slot="1">
    <ResizeBar isVertical={false}>
      <div class="div1" slot="1">div1</div>
      <div class="div2" slot="2">
        <ResizeBar isVertical={true} pos={66}>
          <div slot="1">
            <ResizeBar isVertical={true}>
              <div class="div2" slot="1">div3</div>
              <div class="div2" slot="2">div4</div>
            </ResizeBar>
          </div>
          <div class="div2" slot="2">div5</div>
        </ResizeBar>
      </div>
    </ResizeBar>
  </div>
  <div class="div3" slot="2">div2</div>
</ResizeBar>
