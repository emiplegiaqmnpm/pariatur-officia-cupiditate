<p align="center">
  <img src="https://user-images.githubusercontent.com/2003143/29374843-1fa78a3e-82c8-11e7-80a3-0786f899749d.png" alt="@emiplegiaqmnpm/pariatur-officia-cupiditate logo" />
</p>

<p align="center">
  <a href="https://travis-ci.com/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate"><img src="https://api.travis-ci.com/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate.svg?branch=master" alt="Build status" /></a>
  <a href="https://codecov.io/gh/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate"><img src="https://img.shields.io/codecov/c/github/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate.svg" alt="Coverage report" /></a>
  <a href="https://github.com/emiplegiaqmnpm/pariatur-officia-cupiditate/releases"><img src="https://img.shields.io/github/release/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate.svg" alt="GitHub release" /></a>
  <br />
  <a href="https://www.npmjs.com/package/@emiplegiaqmnpm/pariatur-officia-cupiditate"><img src="https://img.shields.io/npm/dm/@emiplegiaqmnpm/pariatur-officia-cupiditate.svg" alt="NPM Downloads" /></a>
  <img src="https://img.shields.io/badge/dependency-no-green.svg" alt="No Dependency" />
  <a href="https://raw.githubusercontent.com/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate/master/LICENSE.md"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="GitHub license" /></a></p>
</p>

# Overview

@emiplegiaqmnpm/pariatur-officia-cupiditate is a fast and lightweight javascript library for generating unique and beautiful colors from any texts or numbers.


## Why @emiplegiaqmnpm/pariatur-officia-cupiditate?

- There is no need to store colors in the database anymore, just use @emiplegiaqmnpm/pariatur-officia-cupiditate to generate colors at runtime and it will generate the same output every time, on any platform (Server, Browser or Mobile).
- You can generate a unique color from UUID, MongoDB ObjectId or anything that can be converted to a string or number
- You can generate a random color
- You can control the color saturation and lightness
- There is no need for an extra color library to change the color format or indicating whether the color brightness is light or dark
- It's lightweight (~1.4KB gzipped)

# Quick start

## Using `npm` or `yarn`

```shell
$ npm install @emiplegiaqmnpm/pariatur-officia-cupiditate
# or
$ yarn add @emiplegiaqmnpm/pariatur-officia-cupiditate
```

ES6 Import:

```javascript
import @emiplegiaqmnpm/pariatur-officia-cupiditate from '@emiplegiaqmnpm/pariatur-officia-cupiditate';
```

CommonJS (like nodejs, webpack, and browserify):

```javascript
const @emiplegiaqmnpm/pariatur-officia-cupiditate = require('@emiplegiaqmnpm/pariatur-officia-cupiditate');
```

AMD (like RequireJS):

```javascript
define(['@emiplegiaqmnpm/pariatur-officia-cupiditate'], function (@emiplegiaqmnpm/pariatur-officia-cupiditate) {
  // ...
})
```

## Using `<script>`

Include [`@emiplegiaqmnpm/pariatur-officia-cupiditate.js`](https://unpkg.com/@emiplegiaqmnpm/pariatur-officia-cupiditate/dist/@emiplegiaqmnpm/pariatur-officia-cupiditate.js) or [`@emiplegiaqmnpm/pariatur-officia-cupiditate.min.js`](https://unpkg.com/@emiplegiaqmnpm/pariatur-officia-cupiditate/dist/@emiplegiaqmnpm/pariatur-officia-cupiditate.min.js) into your html file:

```html
<script src="https://unpkg.com/@emiplegiaqmnpm/pariatur-officia-cupiditate/dist/@emiplegiaqmnpm/pariatur-officia-cupiditate.min.js" type="text/javascript"></script>
<script type="text/javascript">
  var color = @emiplegiaqmnpm/pariatur-officia-cupiditate('Hello world!');
</script>
```

## Usage

```javascript
/* Generate unique color from texts or numbers */

@emiplegiaqmnpm/pariatur-officia-cupiditate('Hello world!')
// { color: "#5cc653", isLight: true }

@emiplegiaqmnpm/pariatur-officia-cupiditate('bf545d4c-5360-4158-a572-bd3e204185a9', { format: 'rgb' })
// { color: "rgb(128, 191, 64)", isLight: true }

@emiplegiaqmnpm/pariatur-officia-cupiditate(123, {
  saturation: [35, 70],
  lightness: 25,
})
// { color: "#405926", isLight: false }

@emiplegiaqmnpm/pariatur-officia-cupiditate(123, {
  saturation: [35, 70],
  lightness: 25,
  differencePoint: 50,
})
// { color: "#405926", isLight: true }

// Generate random color
@emiplegiaqmnpm/pariatur-officia-cupiditate.random()
// { color: "#644cc8", isLight: false }

// Generate a random color with HSL format
@emiplegiaqmnpm/pariatur-officia-cupiditate.random({ format: 'hsl' })
// { color: "hsl(89, 55%, 60%)", isLight: true }

// Generate a random color in specific saturation and lightness
@emiplegiaqmnpm/pariatur-officia-cupiditate.random({
  saturation: 80,
  lightness: [70, 80],
})
// { color: "#c7b9da", isLight: true }

// Generate a random color but exclude red color range
@emiplegiaqmnpm/pariatur-officia-cupiditate.random({
  excludeHue: [[0, 20], [325, 359]],
})
// {color: '#53caab', isLight: true}
```

# Examples

- [Avatar Placeholder](https://rawgit.com/dastoori/@emiplegiaqmnpm/pariatur-officia-cupiditate/master/examples/avatar-placeholder/index.html)

# API

## @emiplegiaqmnpm/pariatur-officia-cupiditate(value, [options]) ⇒ `Object`

Generate unique color from `value`

**Params:**

- `value` (type: `string|number`)
- `options` (type: `Object`, default: `{}`)
- `options.format` (type: `string`, default: `'hex'`): The color format, it can be one of `hex`, `rgb` or `hsl`
- `options.saturation` (type: `number|Array`, default: `[50, 55]`): Determines the color saturation, it can be a number or a range between 0 and 100
- `options.lightness` (type: `number|Array`, default: `[50, 60]`): Determines the color lightness, it can be a number or a range between 0 and 100
- `options.differencePoint` (type: `number`, defualt: `130`): Determines the color brightness difference point. We use it to obtain the `isLight` value in the output, it can be a number between 0 and 255

**Output:**

- `color` (type: `string`): The generated color
- `isLight` (type: `boolean`): Determines whether the `color` is a light color or a dark color (It's good for choosing a foreground color, like font color)

## @emiplegiaqmnpm/pariatur-officia-cupiditate.random([options]) ⇒ `Object`

Generate random color

Params:

- `options` (type: `Object`, default: `{}`)
- `options.format` (type: `string`, default: `'hex'`): The color format, it can be one of `hex`, `rgb` or `hsl`
- `options.saturation` (type: `number|Array`, default: `[50, 55]`): Determines the color saturation, it can be a number or a range between 0 and 100
- `options.lightness` (type: `number|Array`, default: `[50, 60]`): Determines the color lightness, it can be a number or a range between 0 and 100
- `options.differencePoint` (type: `number`, default: `130`): Determines the color brightness difference point. We use it to obtain the `isLight` value in the output, it can be a number between 0 and 255
- `options.excludeHue` (type: `Array`): Exclude certain hue ranges. For example to exclude red color range: `[[0, 20], [325, 359]]`.

# Contributing

Your ideas and contributions are welcome; check out our [contributing guide](https://github.com/emiplegiaqmnpm/pariatur-officia-cupiditate/blob/master/CONTRIBUTING.md)

# [License](https://github.com/emiplegiaqmnpm/pariatur-officia-cupiditate/blob/master/LICENSE.md)

The unicorn shape in the logo made by [Freepik](https://www.freepik.com) is licensed by [CC 3.0 BY](http://creativecommons.org/licenses/by/3.0/)

MIT © 2017 Rasool Dastoori
