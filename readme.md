# data-animate

HTML DOM-based scroll and GSAP animations.

I was inspired by htmx and created this. I enjoy coding in CSS, and with just basic HTML and CSS knowledge, it's possible to create numerous scroll-triggered animations using this 😎.

Initially, I coded this script for my site-building needs and for simple GSAP or scroll animations. Over time, it started becoming very powerful.

I'm still working on it and testing it in production as well.

This is the initial release. Most features are stable, but I’m still refining it. I’m thinking about resolving the FOUC (Flash of Unstyled Content) problem, though I’m not sure how to implement that yet. I’ll need to run more tests.

If anyone would like to help, please don’t hesitate to contribute or submit a PR. 

I’m quite busy with agency work sometimes. :(

--- > [GitHub: sinanisler/data-animate](https://github.com/sinanisler/data-animate)



## Requirements

It only requires `gsap.js` and `scrolltrigger.js`. That’s it.

I’m considering supporting other JS libraries for additional features, but abstraction needs to stay clean and smart like this. Otherwise, coding animations could become a hassle.

---

## How it Works?

It’s simple! 

### Basic Example
```html
<div data-animate="opacity:0"></div>
```

### Style Start and End Example
This works for almost any CSS property:
```html
<div data-animate="style_start-color:red,style_end-color:green"></div>
```

### Animation Chaining Example
You can chain multiple animations:
```html
<div data-animate="style_start-color:red,style_end-color:green; opacity:0"></div>
```

And that’s it!

Have fun!



# Features 



 
# Main `data-animate` Properties

| **Property**          | **Description**                                                                                          | **Example Value**        |
|-----------------------|----------------------------------------------------------------------------------------------------------|--------------------------|
| `style_start-*`       | Initial CSS styles applied before the animation starts. Replace `*` with the CSS property name. All JavaScript style CSS objects work (e.g., `fontSize`, `borderWidth`, `backgroundColor`). You can set these dynamically. If omitted, the element’s initial DOM state will be used as `style_start`. | `style_start-fontSize:20px`  |
| `style_end-*`         | Final CSS styles applied after the animation ends. Replace `*` with the CSS property name. Works with any valid JavaScript CSS style property. | `style_end-color:blue`   |
| `scroll:false`        | Disables scroll-based triggers, making the animation play only on manual or programmatic triggers.       | `scroll:false`           |
| `splittext`           | Splits the element’s text into characters wrapped in spans, enabling animations per character.            | `splittext:true`         |
| `start`               | Defines the start point of the scroll-triggered animation in ScrollTrigger format.                       | `start:'top 60%'`        |
| `end`                 | Defines the end point of the scroll-triggered animation in ScrollTrigger format.                         | `end:'bottom 40%'`       |
| `x`                   | Defines the horizontal translation distance in pixels. Positive values move right, negative move left.   | `x:100`                  |
| `y`                   | Defines the vertical translation distance in pixels. Positive values move down, negative move up.        | `y:-50`                  |
| `o`, `opacity`        | Specifies the opacity of the element. Values range from `0` (transparent) to `1` (fully visible).         | `o:0.5` or `opacity:0.8` |
| `s`, `scale`          | Sets the scale of the element. Values below `1` shrink the element, and values above `1` enlarge it.      | `s:1.5` or `scale:0.8`   |
| `r`, `rotate`         | Defines the rotation of the element in degrees. Positive values rotate clockwise, negative counterclockwise. | `r:90` or `rotate:-45`   |
| `duration`            | Duration of the animation in seconds.                                                                    | `duration:2s`            |
| `delay`               | Delay before the animation starts, in seconds.                                                           | `delay:0.5s`             |
| `stagger`             | Time delay between the animations of child elements when `splittext` is used.                            | `stagger:0.2`            |
| `scroll`              | Enables or disables scroll-triggered animation. Use `true` to enable scroll-based triggers.              | `scroll:true`            |
| `trigger`             | Specifies whether the animation is manually triggered (e.g., via a button or link).                     | `trigger:true`           |
| `scrub`               | Determines whether the animation is scrubbed (linked to the scroll progress). Can be `true`, `false`, or a number indicating scrub delay. | `scrub:true` or `scrub:1` |
| `pin`                 | Specifies whether the element is pinned during the animation.                                            | `pin:true`               |
| `markers`             | Enables or disables debugging markers for ScrollTrigger.                                                 | `markers:true`           |
| `toggleClass`         | A CSS class to toggle when the animation starts or ends.                                                 | `toggleClass:'active'`   |
| `pinSpacing`          | Controls spacing behavior when an element is pinned.                                                     | `pinSpacing:'margin'`    |

---

## Key Notes About `style_start` and `style_end`

1. **JavaScript Style Compatibility**:
   - Both `style_start` and `style_end` work seamlessly with any valid JavaScript CSS style object.
   - Examples include `fontSize`, `borderWidth`, `borderColor`, `backgroundColor`, and many more.
   - Check this [CSS Reference](https://www.w3schools.com/cssref/index.php) and [CodePen Example](https://codepen.io/sinanisler/pen/XJrzqoY) for a complete list of "most" supported styles. (I dont have time to test all so thats why most supported not all)

2. **Optional `style_start`**:
   - If `style_start` is not provided, the element’s current state in the DOM will automatically be used as the starting style.
   - This simplifies animations where you only need to define the final state (`style_end`).
   - **Personal Recommendation**: Many developers set all initial styles in the DOM (e.g., using CSS frameworks like Bricks) and only define the `style_end`. This approach is minimalistic and efficient.

---

# Separate Table for `data-trigger`

| **Property**          | **Description**                                                                                          | **Example Value**        |
|-----------------------|----------------------------------------------------------------------------------------------------------|--------------------------|
| `data-trigger`        | Specifies the CSS selector of the target element whose animation will be triggered on the trigger element's click event. | `data-trigger: '#myDiv'` |
| **Trigger Element Behavior** | When a `data-trigger` is defined, the trigger element listens for a `click` event. When clicked, it looks up the target element defined in the `data-trigger` value. If the target element has a GSAP animation instance, the animation will be played from the start (`play(0)`). |                      |
| **Target Element**    | The target element must have an animation instance created by the `data-animate` attribute for the trigger to work. |                      |




