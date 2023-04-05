# Responsiveness

---

<!-- .slide: data-auto-animate -->
## Responsiveness
Adjusting for various different screen sizes and viewports.  
Mobile first vs desktop first.

Notes:
Still scary to a lot of people, but shouldn't be.
We have really great and simple tools these days.
Progressive advancement vs graceful degradation.

--

<!-- .slide: data-auto-animate -->
## Responsiveness
- Consider responsiveness from the start (both in design and development).
- Know the context - which devices are your potential clients using?
- Pick a few specific breakpoints based on those devices, optimize for them.
- Use variables and mixins, create a system.
- More granular adjustments are fine too, if needed!

Notes:
It's quite difficult to add responsiveness on top later. For example with older applications.
Layout needs to be redone to use flex/grid etc. Might need mobile specific components.
It's really important to consider responsiveness from the start. Know your audience and the 
devices you need to target, optimize for those breakpoints.
Responsiveness is one of those things that can be a big timesink, so it's important to have a system.

---

<!-- .slide: data-auto-animate -->
## Media queries
Our main tool for creating responsiveness.

```css
@media screen and (min-width: 481px) and (max-width: 768px) {
    .dog {
        width: 100%;
    }
}
```

- Media types: all (default, can be blank) | screen | print | speech
- Media features: min-width | max-width | orientation | ...
- Operators: and | or | not

Note:
- You don't have to write the type.
- You don't have to specify a range of multiple features.
- There's a lot more features, check MDN for a full list.

--

<!-- .slide: data-auto-animate -->
## Media queries
New simpler range syntax.

```css
@media (481px <= width <= 768px) {
    .dog {
        width: 100%;
    }
}

@media (width > 768px) {
    .dog {
        width: 100%;
    }
}
```

Note:
- Make sure to check support before using

---

<!-- .slide: data-auto-animate -->
## Container queries
An alternative to media queries.  
Apply styles to an element based on the size of its container.  
Opens up amazing new options for more modular design.

```css
.card {
  container-type: inline-size;
}

h2 {
  font-size: 1em;
}

@container (min-width: 768px) {
  h2 {
    font-size: 2em;
  }
}
```

Note:
- Similar syntax to media queries
- Need to define a containment context on the parent container
- Then create a container query on the desired children, and it will apply based on the nearest ancestor
with a containment context
- You can also name containment contexts and then target them by name, giving you the ability to change
the styles inside a component based on what container its in
- Make sure to check support before using

---

<!-- .slide: data-auto-animate -->
## Responsive images
`<picture>` lets you provide multiple versions of an image for different display/device scenarios.

```html
<picture>
  <source srcset="img/illustration-large" media="(min-width: 769px)" />
  <source srcset="img/illustration-medium" media="(min-width: 481px)" />
  <img src="img/illustration-small" alt="Illustration" />
</picture>
```

- Optimized image sizes for different screen sizes
- Different image formats based on support
- Art direction choices

Note:
- Provide different srcsets for different scenarios
- Save bandwidth by providing optimized images (size and format)
- Show less detailed/complex images for smaller screens

---

<!-- .slide: data-auto-animate -->
## Responsive typography
- Using em, rem units.
- Be careful not to compromise readability.