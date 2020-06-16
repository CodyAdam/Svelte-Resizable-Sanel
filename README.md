This is a [Svelte](https://svelte.dev) apps.

# Try the demo here : [codyadam.github.io/Svelte-Resizable-Panel](https://codyadam.github.io/Svelte-Resizable-Panel/)

## What is this ?

This is a single Svelte component that allow you to make custom resize bar for your panels.

## How to use

##### You just need to import :

`import ResizeBar from "./ResizeBar.js";`

##### You can use props for more customization :

(e.g. `<ResizeBar isVertical={false} pos={70} thickness={3} min={30} max={60}> [...]`)

-   `isVertical` boolean to choose either a vertical or horizontal bar (false by default)
-   `pos` area where the bar should be placed at the start in percent (50% by default)
-   `thickness` the resize bar thickness in pixels (5px by default)
-   `min` the minimum % position of the bar (10% by default)
-   `max` the maximum % position of the bar (90% by default)

![Screen of the code](https://github.com/CodyAdam/Svelte-Resizable-Sanel/blob/master/ScreenCode.png?raw=true)

![Gif demo](https://github.com/CodyAdam/React-Resizable-Panel/blob/master/demo.gif?raw=true)
