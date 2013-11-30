# Zoomerang.js

Zoom in, zoom out on (almost) anything in your page.

[Demo]()

## Basic Usage

``` js
Zoomerang.listen('#my-image')
```

Now when you click on `#my-image`, it will... of course, zoom in. When you click again, it will zoom back out to its original place. (get it?)

This is largely inspired by [Medium](http://medium.com)'s avatar zoom in effect, with improvements (you can resize / scroll the page and it still works).

## Caveats

- CSS Transform required. (basically, IE10+)
- Works best on fixed size elements such as `display: block`, `display: inline-block` and `img` elements.
- Avoid using it on long inline text that has natural line wraps.

## API Reference

#### Zoomerang.listen(selector | element)

Attach click listeners to all matched elements. You can also directly pass in a single node to this method.

#### Zoomerang.open(selector | element)

Zoom in on the matched element.

#### Zoomerang.close()

Zoom out if currently zoomed-in.

#### Zoomerang.config(options)

Available options (all options take valid CSS values):

- transitionDuration - default: '.4s'
- transitionTimingFunction - default: 'cubic-bezier(.4,0,0,1)'
- bgColor - default: '#fff'
- bgOpacity - default: 1
- maxWidth - max element width when zoomed-in. default: 300
- maxHeight - max element height when zoomed-in. default: 300
- deepCopy - whether to copy innerHTML. If target element has complicated inner structure you might need this to make it work. default: false

## License

MIT