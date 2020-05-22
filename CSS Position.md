### position: static;
Static positioned elements are not affected by the top, bottom, left, and right properties.
### position: fixed;
An element with `position: fixed;` is positioned relative to the viewport. A fixed element does not leave a gap in the page where it would normally have been located.
### position.absolute;
An element with `position: absolute;` is positioned relative to the **nearest positioned ancestor**. However, if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with pages scrolling.
*Note:** A "positioned" element is one whose position is anything except `static`.
### Overlapping Elements
The z-index property specifies the stack order of an element.
```
img {
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: -1;
}
```
Because the image has a z-index of -1, it will be placed behind other elements with greater stack order.
**Note:** If two positioned elements overlap without a z-index specified, the element positioned last in the HTML code will be shown on top.
