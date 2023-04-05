# CSS Colors

--

## New RGB syntax

`rgb(255, 255, 255)`  
is equivalent to  
`rgb(255 255 255)`

Note:
You don't need commas!

--

## Alpha can be specified in `rgb()`

`rgba(255, 255, 255, 0.5)`  
is equivalent to  
`rgb(255 255 255 / 0.5)`

Note:
The old variant still works

--

## The sRGB color space

```css
body {
  background-color: maroon;
  background-color: #800000;
  background-color: rgb(128, 0, 0);
  background-color: hsl(0, 100%, 25.1%);
  background-color: hwb(0 0% 49.8%);
}
```

--

## Display P3

```css
div {
  background-color: color(display-p3 1 0.5 0 / .5);
}
```

(Made by Apple)

Note:
This color space covers 26% more of the visible light spectrum than sRGB.  
Made by Apple and still experimental in Firefox.

--

## Browsers are adding perceptual color models

- LAB color model - Lightness, A-axis, B-axis
- LCH color model - Lightness, Chroma, Hue

```css
p {
  color: lch(52.2345% 72.2 56.2 / .5);
}
```

Note:
LAB color model covers even more than Display P3  
LCH is more intuitive on the web

Chroma (amount of color)

--

## Gradients

https://css-tricks.com/css3-gradients

Note:
Gradients have been around for a long time, but there have been some recent updates
- Radial gradient has a new dedicated radial-gradient function
- Conic Gradients - Creates a gradient around the central point
- Repeating gradients

When you need the details, check CSS-Tricks and MDN

Because you can specify multiple backgrounds for an element,  
you can layer several gradients on top of each other for complex patterns

--

## Color mixing

```css
div {
  background-color: color-mix(in srgb, #34c9eb 25%, white);
}
```

Note:
- Not supported in Firefox yet
- That's very useful, especially with variables
- By default, color transitions happen in the sRGB space. Use color-mix to prevent unexpected colors from appearing.

--

## Colors in CSS transitions

```css
button {
  background-color: rgba(255, 255, 128, 1);
  transition: background-color 1s ease;
}

.bad      { background-color: transparent             }
.also-bad { background-color: rgba(0, 0, 0, 0);       }
.good     { background-color: rgba(255, 255, 128, 0); }
```

Note:
The color still matters when fading to a transparent color.  
Imagine a scenario where we make a button disappear.  
In the bad and also-bad cases,  
the black color will be mixed in during the transition.
