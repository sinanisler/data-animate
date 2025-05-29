

# data-animate

**Simple, declarative scroll & GSAP animations for HTML DOM.**

I created **data-animate** to enable powerful GSAP/ScrollTrigger animations using only HTML and CSS knowledge. Inspired by [htmx](https://htmx.org), it lets you add advanced animations to your website without writing JavaScript for each effect.

This project started as a tool for my own site-building workflow and has grown into a robust, production-ready utility. Most features are stable, but ongoing improvements and testing are happening—feedback and contributions are welcome!

If you want to help, open a [GitHub issue](https://github.com/sinanisler/data-animate/issues) or submit a pull request.
**[View on GitHub → sinanisler/data-animate](https://github.com/sinanisler/data-animate)**

---

## Requirements

* [GSAP (GreenSock Animation Platform)](https://greensock.com/gsap/)
* [GSAP ScrollTrigger plugin](https://greensock.com/scrolltrigger/)

No other dependencies required!

---

## How It Works

Just add a `data-animate` attribute to any HTML element and describe your animation(s) using simple, comma-separated property pairs.

### Basic Example

```html
<div data-animate="opacity:0"></div>
```

### Styling Start and End Example

```html
<div data-animate="style_start-color:red,style_end-color:green"></div>
```

### Chained Animations

Chain multiple animation steps with semicolons:

```html
<div data-animate="style_start-color:red,style_end-color:green; opacity:0"></div>
```

And that’s it! You can create complex scroll-based or programmatic animations without JavaScript.

---

## Features

* **Declarative:** Animate with attributes in your HTML.
* **Works with GSAP + ScrollTrigger:** Full power of these libraries, zero boilerplate.
* **Chain Animations:** Sequence multiple animation steps.
* **Split Text Animations:** Animate by character, word, or line.
* **Device-Aware:** Enable/disable animations on desktop, tablet, or mobile.
* **Trigger Manually:** Trigger any animation with a click via `data-trigger`.
* **Advanced Scroll Settings:** Supports ScrollTrigger’s `start`, `end`, `scrub`, `pin`, and more.
* **Custom Easing, Duration, Delay, Stagger:** All common animation controls.
* **Programmatic Control:** Play, pause, loop, and repeat animations as needed.
* **No JS Required for Typical Use:** Just markup and optional CSS!

---

## Usage

Add `gsap.js`, `ScrollTrigger.js`, and your `data-animate` script. Then use the attributes below.

---

### Main `data-animate` Properties

| Property        | Description                                                                   | Example Value               |
| --------------- | ----------------------------------------------------------------------------- | --------------------------- |
| `style_start-*` | Initial CSS style(s) before animation. Use JS-style property names.           | `style_start-fontSize:20px` |
| `style_end-*`   | Final CSS style(s) after animation. Use JS-style property names.              | `style_end-color:blue`      |
| `scroll:false`  | Disables scroll trigger. Animation only runs manually/programmatically.       | `scroll:false`              |
| `splittext`     | Splits text for character/word/line animation. Use `true`, `word`, or `line`. | `splittext:true`            |
| `start`         | ScrollTrigger’s start value.                                                  | `start:top 60%`             |
| `end`           | ScrollTrigger’s end value.                                                    | `end:bottom 40%`            |
| `x`             | Horizontal translation (pixels).                                              | `x:100`                     |
| `y`             | Vertical translation (pixels).                                                | `y:-50`                     |
| `o`, `opacity`  | Opacity (0 = transparent, 1 = visible).                                       | `o:0.5` / `opacity:0.8`     |
| `s`, `scale`    | Scale factor (1 = normal).                                                    | `s:1.5` / `scale:0.8`       |
| `r`, `rotate`   | Rotation (degrees).                                                           | `r:90` / `rotate:-45`       |
| `duration`      | Animation duration (seconds).                                                 | `duration:2s`               |
| `delay`         | Delay before animation (seconds).                                             | `delay:0.5s`                |
| `stagger`       | Delay between staggered children (seconds).                                   | `stagger:0.2`               |
| `scroll`        | Enables/disables scroll-triggered animation (`true` or `false`).              | `scroll:true`               |
| `trigger`       | Enables manual triggering (e.g., by click).                                   | `trigger:true`              |
| `scrub`         | Links animation progress to scroll (`true`, `false`, or number for delay).    | `scrub:true` / `scrub:1`    |
| `pin`           | Pins element during scroll.                                                   | `pin:true`                  |
| `markers`       | Enables debugging markers.                                                    | `markers:true`              |
| `toggleClass`   | Adds/removes a class when animation starts/ends.                              | `toggleClass:active`        |
| `pinSpacing`    | Spacing mode for pinned elements.                                             | `pinSpacing:margin`         |
| `desktop`       | Enables/disables animation on desktop (`true`/`false`).                       | `desktop:false`             |
| `tablet`        | Enables/disables animation on tablet (`true`/`false`).                        | `tablet:true`               |
| `mobile`        | Enables/disables animation on mobile (`true`/`false`).                        | `mobile:false`              |
| `ease`          | Easing function for the animation.                                            | `ease:power1.inOut`         |
| `rand`          | Randomizes `x`, `y`, or `rotate` values if set to `true`.                     | `rand:true`                 |
| `loop`          | Loops animation if scroll is disabled.                                        | `loop:true`                 |

**Note:** All properties can be chained using semicolons `;` for multi-step animations.

---

### About `style_start` and `style_end`

* Any valid JavaScript-style CSS property can be animated.
* If `style_start` is omitted, the current DOM style is used as the starting state.
* You can set initial styles in your CSS framework or markup and only define the `style_end` for minimal config.

---

## Manual Animation Trigger

You can manually trigger animations using the `data-trigger` attribute:

| Property       | Description                                                                         | Example Value           |
| -------------- | ----------------------------------------------------------------------------------- | ----------------------- |
| `data-trigger` | CSS selector of the element whose animation will play when this element is clicked. | `data-trigger:"#myDiv"` |

**How it works:**

* Add `data-trigger="#targetElement"` to any clickable element.
* When clicked, it will play the GSAP animation of the target element with `data-animate`.

---

## Examples

```html
<!-- Scroll-triggered fade in -->
<div data-animate="opacity:0,style_end-opacity:1"></div>

<!-- Manual trigger on button click -->
<div id="targetDiv" data-animate="x:-200,style_end-x:0,scroll:false"></div>
<button data-trigger="#targetDiv">Animate!</button>

<!-- Animate each character with stagger -->
<h2 data-animate="splittext:true,opacity:0,style_end-opacity:1,stagger:0.04"></h2>
```

---

## Contributing

* Code improvements, bug fixes, and PRs are welcome!
* If you have feature requests, suggestions, or want to help with FOUC (Flash of Unstyled Content), please submit an issue or PR.

---

## License

GPL

---

## Credits

Built and maintained by [@sinanisler](https://github.com/sinanisler).
Inspiration: [htmx](https://htmx.org), [GSAP](https://greensock.com/gsap/).

---

**Happy animating!** 🎉
