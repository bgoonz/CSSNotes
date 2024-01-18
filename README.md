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
  background-image: linear-gradient(to right bottom, #7ed56fb4, #28b485c4),
    url(./../img/hero.jpg);
  background-size: cover;
  background-position: top;
  clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
}
```

#### Clip-Path Helper tool [Clippy](https://bennettfeely.com/clippy/)
