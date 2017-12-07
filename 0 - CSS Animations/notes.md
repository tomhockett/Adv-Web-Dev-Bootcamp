# CSS Animations

## Pseudo-classes

[MDN Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). For example, :hover can be used to change a button's color when the user hovers over it.

```css
div:hover {
  background-color: #F89B4D;
}
```

### :hover

The :hover CSS pseudo-class matches when the user interacts with an element with a pointing device, but does not necessarily activate it. It is generally triggered when the user hovers over an element with the cursor (mouse pointer).

```css
/* Selects any <a> element when "hovered" */
a:hover {
  color: orange;
}
```

### :focus

The :focus CSS pseudo-class represents an element (such as a form input) that has received focus. It is generally triggered when the user clicks or taps on an element or selects it with the keyboard's "tab" key.

```css
/* Selects any <input> when focused */
input:focus {
  color: red;
}
```

### :active

The :active CSS pseudo-class represents an element (such as a button) that is being activated by the user. When using a mouse, "activation" typically starts when the user presses down the primary mouse button and ends when it is released. The :active pseudo-class is commonly used on `<a>` and `<button>` elements, but may be used on other elements, too.

```css
/* Selects any <a> that is being activated */
a:active {
  color: red;
}
```

## Transform Property

[MDN Transform Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/transform?v=control)

The transform CSS property lets you modify the coordinate space of the CSS visual formatting model. Using it, elements can be translated, rotated, scaled, and skewed. It lets you move, warp, rotate, and scale elements.

```css
/* Keyword values */
transform: none;

/* Function values */
transform: translate(12px, 50%);
transform: translateX(2em);
transform: translateY(3in);
transform: scale(2, 0.5);
transform: scaleX(2);
transform: scaleY(0.5);
transform: rotate(0.5turn);
```

### Translation

Essentially 'moving stuff around'

```css
div {
  /* takes all dives and shifts over on the x-axis 100px */
  transform: translateX(100px);
}
```

`transform` is the **property**, and `translateX` is the **function**

### Scaling

Increases or decreases the size of an element.

```css
div {
  /* doubles size of divs */
  transform: scale(2);
}
```

The property will be scaled from the center of the element, but that can be changed

#### Transform-origin

The transform-origin property lets you modify the origin for transformations of an element. For example, the transformation origin of the rotate() function is the center of rotation. (This property is applied by first translating the element by the negated value of the property, then applying the element's transform, then translating by the property value.)

```css
div {
  /* scale doubles on the x-asis and quintuples on the Y*/
  transform: scale(2, 5);
  /* sets the origin on the left bottom corner*/
  transform-origin: left bottom;
}
```

### Rotations

```css
/* Positive degs will be clockwise, negative is counter */
div {
  transform: rotate(45deg);
  /* and the origin can be changed as well; center is default */
  transform-origin: top left;
}
```

Multiple transforms will override each other with the last one undoing the transform done by the first declaration.  The way around this is to combine the 2 transforms into one declaration.

```css
div {
  /* rotate 90deg clockwise and decress scale by half */
  transform: rotate(90deg) scale(0.5);
}
```

### Vendor Prefixes

[MDN on Vendor Prefixes](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix)

Browser vendors sometimes add prefixes to experimental or nonstandard CSS properties and JavaScript APIs, so developers can experiment with new ideas while—in theory—preventing their experiments from being relied upon and then breaking web developers' code during the standardization process. Developers should wait to include the un-prefixed property until browser behavior is standardized.

```md
**THESE ARE A HUGE PAIN IN THE ASS AS THEY CONSTANTLY CHANGE**
```

**SO WHAT CAN WE DO???**

```md
USE AN AUTO-PREFIXER!
```

[Autoprefixer](autoprefixer.github.io) - copy/paste your css here

[Pleeease](http://pleeease.io/) - a Node.js tool

## CSS Transitions

Transitions allow us to control the animation speed, timing, acceleration and a few more when changing css properties on certain elements.

### Transition Properties

* Transition-Duration (how long the change takes)
* Transition-Property (you can specify which properties to change)
* Transition-Timing-Function (the acceleration of the transition)
* Transition-Delay (how long do you wait until the transition starts?)

### Transition-Duration

How long should this transition take?

```css
transition-duration: 1s;
transition-duration: 0.5s; /* you can use decimals */
transition-duration: 3s, 1s; /* we will get to this */
```

### Transition-Property

This specifies the names of CSS properties to which a transition effect should be applied.

```css
transition-property: background;
transition-property: opacity;
transition-property: transform;
transition-property: all; /* this is default functionality */
transition-property: color, opacity; /* no limit on commas here */
```

### Transition-Delay

How long of a delay before the transition starts?

```css
transition-delay: 4s;
transition-delay: 5ms, 10s;
```

### Transition-Timing-Function

Basically controls the acceleration of our transitions

```css
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: linear;
/* and even */
transition-timing-function: cubic-bezier(0.95, 0.050, 0.795, 0.035);
```