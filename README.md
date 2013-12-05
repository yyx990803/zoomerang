# Zoomerang.js

Zoom in, zoom out on (almost) anything in your page.

[Demo](http://yyx990803.github.io/zoomerang/)

## Basic Usage

``` js
Zoomerang.listen('#my-image')
```

Now when you click on `#my-image`, it will... of course, zoom in. When you click again, it will zoom back out to its original place. (get it?)

This is largely inspired by [Medium](http://medium.com)'s avatar zoom in effect, with improvements (you can resize / scroll the page when it's zoomed in and it still works).

## Installation

Zoomerang.js is packaged with UMD so you can use it with most existing module systems. It's also registed as a Bower/NPM/Component package so you can use it with your preferred tools:

``` bash
$ component install yyx990803/zoomerang
# or
$ bower install zoomerang
# or
$ npm install zoomerang
```

## Caveats

- CSS Transform required. (basically, IE10+)
- Works best on fixed size elements such as `display: block`, `display: inline-block` and `img` elements.
- Avoid using it on long inline text that has natural line wraps.
- When used on mobile, it's best to avoid auto font size adjustments (e.g. set scale fixed to 1).

## API Reference

- #### Zoomerang.listen(selector | element)

  Attach click listeners to all matched elements. You can also directly pass in a single node to this method.

- #### Zoomerang.open(selector | element)

  Zoom in on the matched element.

- #### Zoomerang.close()

  Zoom out if currently zoomed-in.

- #### Zoomerang.config(options)

  Takes an options object. Available options (all options take valid CSS values):

    - `transitionDuration` - default: `'.4s'`
    - `transitionTimingFunction` - default: `'cubic-bezier(.4,0,0,1)'`
    - `bgColor` - default: `'#fff'`
    - `bgOpacity` - default: `1`
    - `maxWidth` - max element width when zoomed-in. default: `300`
    - `maxHeight` - max element height when zoomed-in. default: `300`
    - `deepCopy` - whether to copy innerHTML. If target element has complicated inner structure you might need this to make it work. default: `false`

## License

MIT