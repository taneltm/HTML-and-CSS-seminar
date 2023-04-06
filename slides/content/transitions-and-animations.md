# Transitions and animations

---

<!-- .slide: data-auto-animate -->
## Transitions
Transitioning between two property values smoothly over a given duration.  
- Mainly used for state and hover transitions.
- Easy way to create a feeling of extra polish or flair.

Notes:
Something I use a lot, and if I see UIs without it they feel lazy.

--

<!-- .slide: data-auto-animate -->
## Transitions

```css
.dog {
    color: white;
    transition: color 1s ease-out;
}

.dog:hover {
    color: brown;
    transition: color 1s ease-out;
}
```

- Don't forget to apply a transition both ways!
- Some properties cannot be transitioned.
- You can transition multiple properties at once.
- Consider the context - is a transition fitting and does it hurt UX?
- Transitions should be part of the design system, be consistent.
- For positioning and sizing changes, transition transforms.

Notes:
- :hover is the TO transform, .dog is the BACK transform.
- Properties that can be transitioned will have "Animatable: yes" in the docs.
- Can't - most longhand properties, display, position.
- Transitions should be thought-out and part of the design system.
- Functions: linear | ease-in | ease-out | ease-in-out | bezier curves
- Easy to hurt UX if transitions are too slow or unnecessary.
- Create variables or mixins for the timings and transition functions.
- We will practice creating transitions later in the workshop.

---

<!-- .slide: data-auto-animate -->
## Animations
Gradually change an element from one style to another.
- Similar to transition, but you have finer control.
- Create keyframed animations.
- Create a modular animation system.
- Control when and how an animation runs.

Notes:
- For a long time, we had animation libraries for doing this.
- Some are still relevant and used, e.g GSAP, for its complex capabilities and performance,
but CSS animation is pretty powerful and easy to use now.
- You have better control over the animation itself with keyframes, you can control how the animation
is triggered and whether it loops, how many times it runs etc.
- Animations are becoming more important to stand out in the web industry, whole profession of micro-interactions.

--

<!-- .slide: data-auto-animate -->
## Animations

```css
@keyframes fadeIn {
    0% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

.dog {
    animation-name: fadeIn;
    animation-duration: 2s;
    animation-timing-function: ease-out;
    animation-delay: 1s;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
}

.dog {
    animation: fadeIn 2s ease-out 1s forwards;
}
```

Notes: 
- Common case to demonstrate would be a fade-in animation.
- Define a keyframe first, you can name it, set a duration, delay, easing function, 
- When using SCSS or such, put your keyframe animations in a separate file, build a system.
- More different options, check docs for more specific needs.