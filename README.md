# PostCSS For Plugin
[![Build Status](https://travis-ci.org/antyakushev/postcss-for.svg)][ci] [![NPM version](https://badge.fury.io/js/postcss-for.svg)][npm] [![Dependency Status](https://gemnasium.com/antyakushev/postcss-default-unit.svg)][deps]

[PostCSS] plugin that enables `@for` loop syntax in your CSS.

## Try it out!

You can use postcss-for directly from [codepen]. 
Just add [PostCSS] to the pen and add it with `@use postcss-for` syntax, or pick desired [PostCSS] plugins from the list.

[
    ![lalala](https://raw.githubusercontent.com/antyakushev/postcss-for/9a8663762bdb65f94a054926e2eba3b0d8f89c68/resources/codepen.png)
](http://codepen.io/antyakushev/pen/oxOBEO)

## Usage

```js
postcss([ require('postcss-for') ])
```

Note, that unlike the Sass `@for`, postcss-for in the example below iterates from 1 to 3 *inclusively*.
```css
@for $i from 1 to 3 {
    .b-$i { width: $(i)px; }
}
```

```css
.b-1 {
    width: 1px
}
.b-2 {
    width: 2px
}
.b-3 {
    width: 3px
}
```

This plugin must be set before [postcss-nested] and [postcss-simple-vars]. 
Therefore dollar variable cannot be used as a loop range parameter.
If you do want to use predefined range parameters though, consider using [postcss-custom-properties] with [postcss-at-rules-variables], or look into this [postcss-for fork](https://github.com/xori/postcss-for).

`By` keyword is available:

```css
@for $i from 1 to 5 by 2 {
    .b-$i { width: $(i)px; }
}
```

```css
.b-1 {
    width: 1px
}
.b-3 {
    width: 3px
}
.b-5 {
    width: 5px
}
```



See [PostCSS] docs for examples for your environment.

[PostCSS]:                   https://github.com/postcss/postcss
[postcss-nested]:            https://github.com/postcss/postcss-nested
[postcss-simple-vars]:       https://github.com/postcss/postcss-simple-vars
[postcss-custom-properties]: https://github.com/postcss/postcss-custom-properties
[postcss-at-rules-variables]:https://github.com/GitScrum/postcss-at-rules-variables
[ci]:                        https://travis-ci.org/antyakushev/postcss-for
[deps]:                      https://gemnasium.com/antyakushev/postcss-for
[npm]:                       http://badge.fury.io/js/postcss-for
[codepen]:                   http://codepen.io/antyakushev/pen/oxOBEO
