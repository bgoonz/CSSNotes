# CSS

### CSS Reset:

```css
/* Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

`box-sizing: border-box` is a CSS property that changes the way the width and height of an element are calculated. In standard CSS box model, the width and height of an element are calculated just based on the content of the box. If you add padding or borders to the element, they are added to the specified width and height, making the actual size of the box larger.

However, when you set `box-sizing: border-box`, the width and height properties include the padding and border, but not the margin. This means if you set an element to be a certain width and height, that size will include any border and padding you add, but not the margin. The content area's size is reduced to absorb the padding and border, keeping the overall dimensions of the box consistent with the width and height values specified.

This is very useful in responsive design and when working with grids, as it makes it easier to predict the actual size of elements and how they will fit together on the page.

**Inherited styling**

```css
body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
}
```

- We can apply these general styles to the body element because they will be inherited by it's child elements...

- `vh (unit)` stands for viewport height so 95vh is 95% of the viewport height.

- Setting background image:

```css
.header {
  height: 95vh;
  background-image: url(./../img/hero.jpg);
  background-size: cover;
}
```

- Styling background image:

```css
.header {
  height: 95vh;
  background-image: linear-gradient(to right bottom, #7ed56fb4, #28b485c4), url(./../img/hero.jpg);
  background-size: cover;
  background-position: top;
  clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
}
```

#### Clip-Path Helper tool [Clippy](https://bennettfeely.com/clippy/)

**Centering Text**

```css
.text-box {
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```


- `position: absolute;`: This property is used to position the element absolutely relative to its nearest positioned ancestor (instead of the default static position).

- `top: 40%;` and `left: 50%;`: These properties set the top and left distance of the element from its nearest positioned ancestor. The `top: 40%` is specifically chosen in this case due to a `clip-path` applied on the parent element, which visually reduces its height.

- `transform: translate(-50%, -50%);`: This transformation is crucial for centering. It effectively shifts the element left and upwards by 50% of its own width and height, respectively. This adjustment is necessary because the `top` and `left` properties alone position the element based on its top-left corner, not its center.



---

### Animations:

- Generally, there are two ways to animate in CSS, the `transition` property. 
- keyframes at rule (browsers are only optimized for animating opacity and transform property)
  -  When other properties are animated, such as `width`, `height`, `margin`, `left/top/right/bottom` (in the context of positioning), etc., the browser may need to perform reflows and repaints. This is because changes in these properties can affect how elements are laid out on the page, which can be a more resource-intensive process.
