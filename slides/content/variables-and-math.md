# Math and variables

---

## CSS Units and data types

--

## Textual types

- `<string>`
- `url()`

--

## Numeric types

- `<integer>` (column-count, grid-column, grid-row, z-index)
- `<number>` (1, 1.34, ...)
- `<dimension>` (23px, 15em, ...)
- `<percentage>` (10%, ...)
- `<ratio>` (`<number> / <number>`)
- `<flex>` (12fr, ...)

--

## Other types

- `<length>` (width, height, margin, text-shadow, ...)
- `<angle>` (deg, grad, rad, or turn units)
- `<time>` (s or ms units)
- ...and many more

--

## Units

```css
body {
  background-color: maroon;
  background-color: #800000;
  background-color: hsl(0, 100%, 25.1%);
  background-color: rgb(128, 0, 0);
  background-color: hwb(0 0% 49.8%);
}
```

Note:
A single data type can be expressed by several units or a combination of different units.

Let's come back to the colors a bit later...

---

## Math functions
- `min`, `max`, `clamp`, `calc`
- `sin`, `tan`, `acos`, `asin`, `atan`, `atan2`
- `sqrt`, `pow`, `exp`, `mod`, `log`, `hypot`

Notes:
- Basic math functions
- Trigonometric functions
- Experimental functions

---
<!-- .slide: data-auto-animate -->
## Math basics
```css [1]
.dog { width: calc(100vw / 3);           }
.dog { width: calc(100vw - 40px - 30px); }
.dog { width: min(50vw, 200px);          }
.dog { width: max(20vw, 400px);          }
.dog { width: clamp(200px, 20vw, 400px); }
```

Note:
- Let's go over the basic functions
- You can add, subtract, multiply and divide
- At least one of the values needs to have a unit, in this case viewport-width

--

<!-- .slide: data-auto-animate -->
## Math basics
```css [2]
.dog { width: calc(100vw / 3);           }
.dog { width: calc(100vw - 40px - 30px); }
.dog { width: min(50vw, 200px);          }
.dog { width: max(20vw, 400px);          }
.dog { width: clamp(200px, 20vw, 400px); }
```

Note:
- The function isn't limited to only 2 values

--

<!-- .slide: data-auto-animate -->
## Math basics
```css [3]
.dog { width: calc(100vw / 3);           }
.dog { width: calc(100vw - 40px - 30px); }
.dog { width: min(50vw, 200px);          }
.dog { width: max(20vw, 400px);          }
.dog { width: clamp(200px, 20vw, 400px); }
```

Note:
You can provide 2 values and find the smallest

--

<!-- .slide: data-auto-animate -->
## Math basics
```css [4]
.dog { width: calc(100vw / 3);           }
.dog { width: calc(100vw - 40px - 30px); }
.dog { width: min(50vw, 200px);          }
.dog { width: max(20vw, 400px);          }
.dog { width: clamp(200px, 20vw, 400px); }
```

Note:
...or the largest value

--

<!-- .slide: data-auto-animate -->
## Math basics
```css [5]
.dog { width: calc(100vw / 3);           }
.dog { width: calc(100vw - 40px - 30px); }
.dog { width: min(50vw, 200px);          }
.dog { width: max(20vw, 400px);          }
.dog { width: clamp(200px, 20vw, 400px); }
```

Note:
Finally the clamp function.

Haven't seen it used much outside game development, but it's very useful for the web.  

It combines min and max to constrain the middle value between the minimum and maximum values.

---

<!-- .slide: data-auto-animate -->
## Variables

Note:
Let's check how variables might help make these calculations easier

--

<!-- .slide: data-auto-animate -->
## ~~Variables~~
## Custom properties

Note:
Let's check how variables might help make these calculations easier

--

## Without
```scss []
main {
  width: calc(100vw - 120px);

  @media (min-width: 800px) {
    width: calc(100vw - 320px);
  }
}
```

Note:
Before CSS variables, we would write something like this...

Notice that we substract 120 or 320 pixels, depending on the screen width.

When you read this, it's not immediately clear what the 120px and 320px values represent.

--

## Now with custom properties
```scss [2,6,10]
:root {
  --sidebar-width: 120px;
}

@media (min-width: 800px) {
  --sidebar-width: 320px;
}

main {
  width: calc( 100vw - var(--sidebar-width) );
}
```

Note:
With custom properties, there's less repetition and now it's finally clear what those values represent.

--

## Clearer typography definitions

```scss
:root {
  --font-family-primary:   "Source Sans Pro", sans;
  --font-family-secondary: "Roboto", sans;
  ...
}
```

--

## Names for all the weights!

```scss
:root {
  ...
  --font-weight-thin:       100;
  --font-weight-extralight: 200; /* Ultra Light */
  --font-weight-light:      300;
  --font-weight-normal:     400; /* Regular */
  --font-weight-medium:     500;
  --font-weight-semibold:   600; /* Demi Bold */
  --font-weight-bold:       700;
  ...
}
```

--

```css
:root {
  ...
  --font-body:  var(--font-weight-normal) 16px/24px var(--font-family-primary);
  --font-title: var(--font-weight-semibold) 18px var(--font-family-primary);
  --font-btn:   var(--font-weight-semibold) 16px var(--font-family-secondary);
  --font-link:  inherit;
  ...
}
```