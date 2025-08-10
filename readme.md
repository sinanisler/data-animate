

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

### Examples

---

**1. Scroll-triggered fade in**
Element fades in as it enters the viewport.

```html
<div data-animate="opacity:0,style_end-opacity:1"></div>
```

---

**2. Fade up and in**
Element slides up and fades in on scroll.

```html
<div data-animate="y:50,opacity:0,style_end-y:0,style_end-opacity:1"></div>
```

---

**3. Slide in from the left**
Element slides in from the left and becomes visible.

```html
<div data-animate="x:-200,style_end-x:0,opacity:0,style_end-opacity:1"></div>
```

---

**4. Scale up with fade**
Element scales from 70% and fades in.

```html
<div data-animate="scale:0.7,opacity:0,style_end-scale:1,style_end-opacity:1"></div>
```

---

**5. Rotate and fade in**
Element rotates into place while fading in.

```html
<div data-animate="rotate:-90,opacity:0,style_end-rotate:0,style_end-opacity:1"></div>
```

---

**6. Character stagger animation**
Each character animates in with a delay.

```html
<h2 data-animate="splittext:true,opacity:0,style_end-opacity:1,stagger:0.05"></h2>
```

---

**7. Word-by-word stagger animation**
Each word appears in sequence.

```html
<p data-animate="splittext:word,opacity:0,style_end-opacity:1,stagger:0.15"></p>
```

---

**8. Manual trigger by button click**
Animation runs only when triggered manually.

```html
<div id="box" data-animate="x:300,style_end-x:0,scroll:false"></div>
<button data-trigger="#box">Slide In Box</button>
```

---

**9. Pin element while animating**
Section stays pinned during scroll animation.

```html
<section data-animate="y:100,style_end-y:0,pin:true"></section>
```

---

**10. Color transition**
Text color animates from gray to blue.

```html
<div data-animate="style_start-color:#999,style_end-color:#0066ff"></div>
```

---

**11. Desktop-only animation**
Runs only on desktop devices.

```html
<div data-animate="opacity:0,style_end-opacity:1,desktop:true,tablet:false,mobile:false"></div>
```

---

**12. Tablet-only animation**
Animation occurs only on tablets.

```html
<div data-animate="y:50,style_end-y:0,tablet:true,desktop:false,mobile:false"></div>
```

---

**13. Mobile-only animation**
Animation for mobile screens only.

```html
<div data-animate="x:-100,style_end-x:0,mobile:true,desktop:false,tablet:false"></div>
```

---

**14. Looping animation on load**
Repeats animation forever when scroll is disabled.

```html
<div data-animate="opacity:0,style_end-opacity:1,scroll:false,loop:true"></div>
```

---

**15. Randomized rotation on scroll**
Element rotates from a random angle.

```html
<div data-animate="rotate:30,style_end-rotate:0,rand:true"></div>
```

---

**16. Scrub (scroll-linked) animation**
Animation progress is tied to scroll position.

```html
<div data-animate="x:100,style_end-x:0,scrub:true"></div>
```

---

**17. Slide down with delay**
Element slides down after a short delay.

```html
<div data-animate="y:-100,style_end-y:0,delay:0.8"></div>
```

---

**18. Animate border width**
Border grows from 0px to 4px.

```html
<div data-animate="style_start-borderWidth:0px,style_end-borderWidth:4px"></div>
```

---

**19. Background color fade**
Background animates from gray to yellow.

```html
<div data-animate="style_start-backgroundColor:#eee,style_end-backgroundColor:#ffe082"></div>
```

---

**20. Animate font size**
Text grows larger on scroll.

```html
<div data-animate="style_start-fontSize:14px,style_end-fontSize:32px"></div>
```

---

**21. Border radius animation**
Box becomes more rounded as it animates.

```html
<div data-animate="style_start-borderRadius:0px,style_end-borderRadius:50px"></div>
```

---

**22. Box shadow reveal**
Shadow appears under the box on scroll.

```html
<div data-animate="style_start-boxShadow:none,style_end-boxShadow:0 6px 30px rgba(0,0,0,0.3)"></div>
```

---

**23. Scale up and fade in**
Starts from 0% size and becomes visible.

```html
<div data-animate="scale:0,style_end-scale:1,opacity:0,style_end-opacity:1"></div>
```

---

**24. Fade in button on scroll**
Button appears as user scrolls down.

```html
<button data-animate="opacity:0,style_end-opacity:1"></button>
```

---

**25. Slide in image from bottom**
Image animates upward into place.

```html
<img data-animate="y:150,style_end-y:0,opacity:0,style_end-opacity:1">
```

---

**26. Pin and color change**
Element is pinned and changes color during scroll.

```html
<div data-animate="pin:true,style_start-color:black,style_end-color:red"></div>
```

---

**27. Fade out on scroll**
Element fades away as user scrolls past.

```html
<div data-animate="opacity:1,style_end-opacity:0"></div>
```

---

**28. Animate with custom easing**
Uses a specific GSAP easing curve.

```html
<div data-animate="y:80,style_end-y:0,ease:power3.inOut"></div>
```

---

**29. Staggered animation for child elements**
Each child div animates one after another.

```html
<div data-animate="stagger:0.2,y:30,style_end-y:0">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

---

**30. Opacity bounce with loop**
Element bounces in opacity forever.

```html
<div data-animate="opacity:0,style_end-opacity:1,scroll:false,loop:true,ease:bounce"></div>
```

---

**31. Animate height**
Element grows taller on scroll.

```html
<div data-animate="style_start-height:40px,style_end-height:120px"></div>
```

---

**32. Animate width**
Element widens smoothly.

```html
<div data-animate="style_start-width:40px,style_end-width:120px"></div>
```

---

**33. Fade in and slide right**
Element moves and fades in.

```html
<div data-animate="x:-100,opacity:0,style_end-x:0,style_end-opacity:1"></div>
```

---

**34. Multiple chained animations**
Text color changes, then it fades in.

```html
<p data-animate="style_start-color:#888,style_end-color:#000; opacity:0,style_end-opacity:1"></p>
```

---

**35. Text line splitting animation**
Each line of text animates in.

```html
<div data-animate="splittext:line,opacity:0,style_end-opacity:1,stagger:0.25">
  Line 1<br>Line 2<br>Line 3
</div>
```

---

**36. Slide in with custom scroll start/end**
Animation triggers at a specific scroll position.

```html
<div data-animate="x:-80,style_end-x:0,start:'top 75%',end:'bottom 60%'"></div>
```

---

**37. Animate background gradient**
Background changes to a gradient.

```html
<div data-animate="style_start-background:linear-gradient(#fff,#eee),style_end-background:linear-gradient(#0066ff,#00c2ff)"></div>
```

---

**38. Animate margin**
Element's margin increases on scroll.

```html
<div data-animate="style_start-margin:0px,style_end-margin:30px"></div>
```

---

**39. Animate padding**
Element's padding grows for visual pop.

```html
<div data-animate="style_start-padding:4px,style_end-padding:28px"></div>
```

---

**40. Manual trigger with class toggle**
Class is added when triggered manually.

```html
<div id="myDiv" data-animate="opacity:0,style_end-opacity:1,scroll:false,toggleClass:active"></div>
<button data-trigger="#myDiv">Reveal</button>
```

---

**41. Animate only on desktop and tablet**
No animation on mobile.

```html
<div data-animate="opacity:0,style_end-opacity:1,desktop:true,tablet:true,mobile:false"></div>
```

---

**42. Animate width and color together**
Element grows and changes color.

```html
<div data-animate="style_start-width:60px,style_end-width:200px,style_start-backgroundColor:#ccc,style_end-backgroundColor:#8e44ad"></div>
```

---

**43. Chain multiple effects (move, scale, fade)**
Multiple steps chained.

```html
<div data-animate="x:-80,style_end-x:0; scale:0.6,style_end-scale:1; opacity:0,style_end-opacity:1"></div>
```

---

**44. Animate text underline**
Underline appears as text animates in.

```html
<span data-animate="style_start-textDecoration:none,style_end-textDecoration:underline,opacity:0,style_end-opacity:1"></span>
```

---

**45. Animate list items with stagger**
Each list item fades in sequentially.

```html
<ul data-animate="stagger:0.15,opacity:0,style_end-opacity:1">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
</ul>
```

---

**46. Pin with scrub animation**
Element is pinned and animates with scroll position.

```html
<div data-animate="pin:true,scrub:true,y:200,style_end-y:0"></div>
```

---

**47. Animate using percentage movement**
Move by percentage, not pixels.

```html
<div data-animate="x:100%,style_end-x:0"></div>
```

---

**48. Animate filter: blur**
Image sharpens as it scrolls in.

```html
<img src="img.jpg" data-animate="style_start-filter:blur(8px),style_end-filter:blur(0px)">
```

---

**49. Animate z-index**
Element rises above siblings as it animates.

```html
<div data-animate="style_start-zIndex:1,style_end-zIndex:10"></div>
```

---

**50. Animate letter spacing**
Text expands as it animates in.

```html
<div data-animate="style_start-letterSpacing:0,style_end-letterSpacing:10px"></div>
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
| `scroll:false`  | Disables ScrollTrigger. Animation plays when the element enters the viewport (via IntersectionObserver) or programmatically. | `scroll:false`              |
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
| `trigger`       | Special modes: `true` builds a paused timeline for manual/programmatic play; `body` uses `document.body` as the ScrollTrigger trigger. | `trigger:true` / `trigger:body` |
| `scrub`         | Links animation progress to scroll (`true`, `false`, or number for delay). Default is `1` when scroll is enabled. | `scrub:true` / `scrub:1`    |
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
| `t_start`       | Absolute position of a step in a multi-step timeline (seconds).               | `t_start:0`                 |
| `t_end`         | Absolute end time of a step; if both `t_start` and `t_end` are set, duration is inferred as `t_end - t_start`. | `t_end:1.5`                 |
| `once`          | Play the scroll animation once and disable afterwards.                        | `once:true`                 |

**Note:** All properties can be chained using semicolons `;` for multi-step animations.

---

### About `style_start` and `style_end`

* Any valid JavaScript-style CSS property can be animated.
* If `style_start` is omitted, the current DOM style is used as the starting state.
* You can set initial styles in your CSS framework or markup and only define the `style_end` for minimal config.

#### Alternate style syntax

You can also use a function-like syntax for styles:

```
style_end-scale(1),style_start-rotate(45deg)
```

#### Device breakpoints

Device flags use window width to determine the current device:

- Desktop: ≥ 991px
- Tablet: > 767px and < 991px
- Mobile: ≤ 767px

#### ScrollTrigger defaults

Unless overridden, the library uses sensible defaults:

- `start: top 60%`
- `end: bottom 40%`
- `scrub: 1` (set `scrub:false` to play once when triggered)
- `pinSpacing: margin`

---

## Manual Animation Trigger

You can manually trigger animations using the `data-trigger` attribute:

| Property       | Description                                                                         | Example Value           |
| -------------- | ----------------------------------------------------------------------------------- | ----------------------- |
| `data-trigger` | CSS selector of the element whose animation will play when this element is clicked. | `data-trigger:"#myDiv"` |

**How it works:**

* Add `data-trigger="#targetElement"` to any clickable element.
* When clicked, it will play the GSAP animation of the target element with `data-animate`.

Works with both regular scroll animations and timelines created with `trigger:true`.

---

## Programmatic API

You can create or update animations in JavaScript without writing GSAP code directly.

```
// Select by CSS selector, Element, or NodeList
createDataAnimate('#hero', 'y:80,opacity:0,style_end-y:0,style_end-opacity:1');

// Build a paused timeline and control it
createDataAnimate('#card', 'trigger:true, t_start:0, x:-60, style_end-x:0; t_start:0.8, o:0, style_end-o:1');
```

Notes:

- Calls made before the library is fully initialized are queued and executed automatically after load.
- Re-invoking `createDataAnimate` on the same element replaces the previous animation safely.

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
