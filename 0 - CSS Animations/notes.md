# Pseudo-classes

[MDN Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). For example, :hover can be used to change a button's color when the user hovers over it.

```css
div:hover {
  background-color: #F89B4D;
}
```

## :hover

The :hover CSS pseudo-class matches when the user interacts with an element with a pointing device, but does not necessarily activate it. It is generally triggered when the user hovers over an element with the cursor (mouse pointer).

```css
/* Selects any <a> element when "hovered" */
a:hover {
  color: orange;
}
```

## :focus

The :focus CSS pseudo-class represents an element (such as a form input) that has received focus. It is generally triggered when the user clicks or taps on an element or selects it with the keyboard's "tab" key.

```css
/* Selects any <input> when focused */
input:focus {
  color: red;
}
```

## :active

The :active CSS pseudo-class represents an element (such as a button) that is being activated by the user. When using a mouse, "activation" typically starts when the user presses down the primary mouse button and ends when it is released. The :active pseudo-class is commonly used on `<a>` and `<button>` elements, but may be used on other elements, too.

```css
/* Selects any <a> that is being activated */
a:active {
  color: red;
}
```
