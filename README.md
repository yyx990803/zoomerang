# Zoomerang.js

Zoom in, zoom out on (almost) anything in your page.

[Demo](http://yyx990803.github.io/zoomerang/)

## Basic Usage

Include with a script tag, or install with your package manager of choice (Bower/Component/npm).

``` js
Zoomerang.listen('#my-image')
```

Now when you click on `#my-image`, it will... of course, zoom in. When you click again, it will zoom back out to its original place. (get it?)

This is largely inspired by [Medium](http://medium.com)'s avatar zoom in effect, with improvements (you can resize / scroll the page when it's zoomed in and it still works). Please note it depends on the way browsers handle CSS transforms and has limited compatibility.

## Caveats / Known Issues

- CSS Transform required. (basically, IE10+)
- Works best on fixed size elements such as `display: block`, `display: inline-block` and `img` elements.
- Avoid using it on long inline text that has natural line wraps.
- When used on mobile, it's best to avoid auto font size adjustments (e.g. set scale fixed to 1).
- Elements with non-rectangular shape will have pixelated edge in Firefox.
- Doesn't work on stock Android 2.x browser.

## API Reference

- #### Zoomerang.listen(selector | element)

  Attach click listeners to all matched elements. You can also directly pass in a single node to this method.

- #### Zoomerang.open(selector | element, [callback])

  Zoom in on the matched element. Fires optional callback when the transition is done.

- #### Zoomerang.close([callback])

  Zoom out if currently zoomed-in. Fires optional callback when the transition is done.

- #### Zoomerang.config(options)

  Takes an options object. Available options (all options take valid CSS values):

    - `transitionDuration` - default: `'.4s'`
    - `transitionTimingFunction` - default: `'cubic-bezier(.4,0,0,1)'`
    - `bgColor` - default: `'#fff'`
    - `bgOpacity` - default: `1`
    - `maxWidth` - max element width when zoomed-in. default: `300`
    - `maxHeight` - max element height when zoomed-in. default: `300`
    - `deepCopy` - whether to copy innerHTML. If target element has complicated inner structure you might need this to make it work. default: `false`
    - `onOpen` - a callback function that will be called when a target is zoomed in and transition has ended. It will get the target element as the argument.
    - `onClose` - same as `onOpen`, except fired when zoomed out.
    - `onBeforeOpen` - a callback function, that will be called before zoom-in.
    - `onBeforeClose` - a callback function, that will be called before zoom-out.
## License

MIT

Brought to you by [@youyuxi](https://twitter.com/youyuxi).