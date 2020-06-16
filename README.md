This is a [Svelte](https://svelte.dev) apps.

## What is this ?

This is a single Svelte component that allow you to make custom resize bar for your panels.

## How to use

##### You just need to import :

`import ResizeBar from "./ResizeBar.js";`

##### You can use props for more customization :

(e.g. `<ResizeBar direction="horizontal" position={70} className="bar1" minPos={30} maxPos={60}> [...]`)

-   `isVertical` boolean to choose either a vertical or horizontal bar (false by default)
-   `pos` area where the bar should be placed at the start in percent (50% by default)
-   `thickness` the resize bar thickness in pixels (5px by default)
-   `minPos` the minimum % position of the bar (10% by default)
-   `maxPos` the maximum % position of the bar (90% by default)

![Screen of the code](https://github.com/CodyAdam/Svelte-Resizable-Panel/blob/master/ScreenCode.png?raw=true)

![Gif demo](https://github.com/CodyAdam/React-Resizable-Panel/blob/master/demo.gif?raw=true)
