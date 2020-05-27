To center an image, set left and right margin to `auto`and make it inot a `block` element.

#### Center Vertically - Using line-height
Except using `padding` and `text-align: center`, we can also use the `line-height` property with a value that is equal to the `height` property.

**Example**
```
.center {
  line-height: 200px;
  height: 200px;
  text-align: center;
}
/* If the text has mutiple lines, add the following: */
.center p {
  line-center: 1.5;
  display: inline-block;
  vertical-align: middle;
}
