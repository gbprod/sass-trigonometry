# sass-trigonometry

[![Build Status](https://travis-ci.org/gbprod/sass-trigonometry.svg?branch=master)](https://travis-ci.org/gbprod/sass-trigonometry)
[![License](https://img.shields.io/badge/licence-WTFPL-blue.svg)](http://www.wtfpl.net/)
[![npm version](https://img.shields.io/npm/v/sass-trigonometry.svg?style=flat)](https://www.npmjs.com/package/sass-trigonometry)

Sass trigonometry and inverse trigonometry functions.

## Introduction

Expand Sass function with pure Sass trigonometry functions : `pi` , `deg-to-rad`, `rad-to-deg` , `sin` , `cos` , `tan` , `asin` , `acos` and `atan`.
And with some usefull math functions : `pow`, `fact` and `sqrt`.

It could allows to dynamicly calculate angle in pure sass.

## Install

Using npm
```bash
npm install --save sass-trigonometry
```

Using yarn
```bash
yarn add sass-trigonometry
```

## Usage

```scss
@import "~sass-trigonometry";
```

## Constant

### `pi`

_Example:_
```scss
$pio2: pi() / 2;
```

## Functions

### `deg-to-rad` and `rad-to-deg`
Simple degres to radian conversion functions.

### `sin` , `cos` and `tan`

Sine, Cosine and Tangent trigonometry functions.

_Example_
```scss
sin(45deg); // => 0.7071...
cos(30deg); // => 0.8660...
tan(60deg); // => 1.7320...
```

### `asin` , `acos` and `atan`.

Arcsine, Arccosine and Arctangent inverted trigonometry functions.

_Example_
```scss
asin(0.7071); // => 45
acos(0.8660); // => 30
atan(1.7320); // => 60
```

### `pow`, `fact` and `sqrt`

Power, Factorial and Square-root functions

_Example_
```scss
pow(10, 2); // => 100
fact(5); // => 120
sqrt(100); // => 10
```

## Examples

```scss
@import "~sass-trigonometry";

$width: 200;
$height: 150;
$diagonal-width: sqrt(pow($width, 2) + pow($height, 2));
$diagonal-angle: atan($height / $width);


#triangle {
    position: relative;
    height: #{$height}px;
    width: #{$width}px;
    border-bottom: 1px solid red;
    border-left: 1px solid red;

    &:before {
        border-top: 1px solid red;
        content: "";
        left: 0;
        position: absolute;
        top: $height;
        transform-origin: left;
        transform: rotate(#{$diagonal-angle}deg);
        width: #{$diagonal-width}px;
    }
}
```

[See the result in Codepen](https://codepen.io/gbprod/pen/ZEYyzJM)

## References
 * https://github.com/drewsynan/trig.sass/blob/master/trig.scss
 * https://blog.smarchal.com/sass-et-la-trigonometrie
 * https://web.archive.org/web/20131001093543/http://japborst.net/blog/sass-sines-and-cosines.html
 * https://codepen.io/thebabydino/pen/rvwuF
 * http://thesassway.com/advanced/inverse-trigonometric-functions-with-sass
 * https://gist.github.com/kamikat/c4d472ce3c61feec6376