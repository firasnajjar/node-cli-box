[![cli-box](http://i.imgur.com/6bOa5iy.png)](#)

# cli-box [![Support this project][donate-now]][paypal-donations]

A library to generate ASCII boxes via NodeJS

[![cli-box](http://i.imgur.com/425gC67.png)](#)

## Installation

```sh
$ npm i cli-box
```

## Example

```js
// Dependencies
var Box = require("cli-box");

// Create a simple box
var b1 = Box("20x10");
console.log(b1.toString());

// Set custom marks
var b2 = new Box({
    w: 10
  , h: 10
  , stringify: false
  , marks: {
        nw: "╔"
      , n:  "══"
      , ne: "╗"
      , e:  "║"
      , se: "╝"
      , s:  "══"
      , sw: "╚"
      , w:  "║"
      , b: "░░"
    }
});
console.log(b2.stringify());

// Box with text and use the stringify
var b3 = Box("20x10", "I will be \u001b[31mdis\u001b[0mplayed inside! \n A\u001b[34mnd I'm in a\u001b[0m new line!");
console.log(b3);

// Box with aligned text to top-right
var b4 = Box("30x20", {
    text: "Box content"
  , stretch: true
  , autoEOL: true
  , vAlign: "top"
  , hAlign: "right"
});
console.log(b4);

// Full screen box
var b5 = Box({fullscreen: true, marks: {}}, "Hello World!");
console.log(b5.toString());
```

## Documentation

### `CliBox(options, text)`
Creates a new ASCII box.

#### Params
- **Object|String** `options`: A string representing the size: `WIDTHxHEIGHT` (e.g. `10x20`) or an object:

 - `width` or `w` (Number): The box width.
 - `height` or `h` (Number): The box height.
 - `fullscreen` (Boolean): If `true`, the box will have full size
   (default: `false`).
 - `stringify` (Boolean): If `false` the box will not be stringified (the
   `CliBox` object will be returned instead).
 - `marks` (Object): An object containing mark characters. Default:
    - `nw`: `"+"`
    - `n`: `"-"`
    - `ne`: `"+"`
    - `e`: `"|"`
    - `se`: `"+"`
    - `s`: `"-"`
    - `sw`: `"+"`
    - `w`: `"|"`
    - `b`: `" "`
- **Object|String** `text`: A string to be displayed or an object:
 - `text` (String): The text to be displayed.
 - `stretch` (Boolean): Stretch box to fix text (default: `false`).
 - `autoEOL` (Boolean): Break lines automatically (default: `false`).
 - `hAlign` (String): Horizontal alignement (default: `"middle"`). It can
   take one of the values: `"left"`, `"middle"`, `"right"`.
 - `vAlign` (String): Vertical alignement (default: `"center"`). It can take
   one of the values: `"top"`, `"center"`, `"bottom"`.

#### Return
- **Object|Stringify** The `CliBox` object (if `options.stringify` is `false`) or the stringified box.

### `stringify()`
Returns the stringified box.

#### Return
- **String** Stringified box string.

## How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].

## Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

 - [`artstack-downloader`](https://github.com/IonicaBizau/artstack-downloader)

 - [`ascii-github`](https://npmjs.com/package/ascii-github)

 - [`cli-cal`](https://github.com/fnogatz/cli-cal) by Falco Nogatz

 - [`cli-gh-cal`](https://github.com/IonicaBizau/cli-gh-cal)

 - [`cli-github`](https://github.com/IonicaBizau/cli-github)

 - [`cli-sunset`](https://github.com/IonicaBizau/cli-sunset)

 - [`csk-cli`](https://github.com/joshumax/csk-cli) by Josh Max

 - [`le-table`](https://github.com/IonicaBizau/node-le-table)

 - [`overlap`](https://github.com/IonicaBizau/node-overlap)

 - [`text-animation`](https://github.com/IonicaBizau/text-animation)

## License

[KINDLY][license] © [Ionică Bizău][website]

[license]: http://ionicabizau.github.io/kindly-license/?author=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica@gmail.com%3E&year=2014

[website]: http://ionicabizau.net
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md