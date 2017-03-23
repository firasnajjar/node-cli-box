
[![cli-box](http://i.imgur.com/6bOa5iy.png)](#)

# cli-box

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Version](https://img.shields.io/npm/v/cli-box.svg)](https://www.npmjs.com/package/cli-box) [![Downloads](https://img.shields.io/npm/dt/cli-box.svg)](https://www.npmjs.com/package/cli-box)

> A library to generate ASCII boxes via NodeJS

[![cli-box](http://i.imgur.com/425gC67.png)](#)

## :cloud: Installation

```sh
$ npm i --save cli-box
```


## :clipboard: Example



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

## :question: Get Help

There are few ways to get help:

 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help from me, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:


## :memo: Documentation


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
    - `nw`: `"┌"`
    - `n`:  `"─"`
    - `ne`: `"┐"`
    - `e`:  `"│"`
    - `se`: `"┘"`
    - `s`:  `"─"`
    - `sw`: `"└"`
    - `w`:  `"|"`
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



## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

 - Starring and sharing the projects you like :rocket:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)

Thanks! :heart:


## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:


 - [`3abn`](https://github.com/IonicaBizau/3abn#readme)—A 3ABN radio client in the terminal.
 - [`artstack-downloader`](https://github.com/IonicaBizau/artstack-downloader)—Download artworks from your following users.
 - [`ascii-github`](https://npmjs.com/package/ascii-github)—GitHub CLI Client
 - [`cli-cal`](https://github.com/fnogatz/cli-cal) (by Falco Nogatz)—Github-like calendar graph for the CLI
 - [`cli-gh-cal`](https://github.com/IonicaBizau/cli-gh-cal)—GitHub like calendar graphs in command line.
 - [`cli-github`](https://github.com/IonicaBizau/cli-github)—A fancy GitHub client for command line.
 - [`csk-cli`](https://github.com/joshumax/csk-cli) (by Josh Max)—A command-line client to ClearDarkSky.com, written in Node.js
 - [`fluxmockserverapi`](https://npmjs.com/package/fluxmockserverapi) (by Leo Cuello)—Rest service flux-gal
 - [`ghcal`](https://github.com/IonicaBizau/ghcal)—See the GitHub contributions calendar of a user in the command line.
 - [`le-table`](https://github.com/IonicaBizau/le-table)—Another NodeJS module for creating ASCII tables.
 - [`overlap`](https://github.com/IonicaBizau/node-overlap)—Overlap two strings that contain new lines. Useful for ASCII drawings.
 - [`text-animation`](https://github.com/IonicaBizau/text-animation)—Create beautiful ASCII text animations using NodeJS.

## :scroll: License

[MIT][license] © [Ionică Bizău][website]

[badge_patreon]: http://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: http://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: http://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: http://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2014#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
