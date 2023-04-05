# Selectors, specificity

---

<!-- .slide: data-auto-animate -->
## Selectors
Used to target elements you want to apply styles to.
- ID
- Class
- Attribute (data, title, ...)
- Pseudo classes

--

<!-- .slide: data-auto-animate -->
## Pseudo classes
Specify a special state of the selected element(s).
- ::before, ::after
- :hover, :focus, :active
- :nth-child, :first-child, :last-child, :nth-of-type
- :checked, :disabled, :required
- ::marker, ::placeholder, ::selection
- :is(), :not(), :where(), :has()

Note:
I'd like to point out the final ones on the list here, which create a ton of new opportunities.

--

<!-- .slide: data-auto-animate -->
## Combinators
Describe a relationship between selectors.  
You can use these relationships for more complex targeting.
```css
div p { color: blue; }

div > p { color: blue; }

div + p { color: blue; }

div ~ p { color: blue; }
```

Note:
You can also use combinators for more complex targeting.
- Descendant - most common - target all elements that are inside parent, no matter how deep
- Direct child - target all elements that are directly inside parent, one level
- Adjacent sibling - target the next sibling after element
- General sibling - target all next siblings after element

---

<!-- .slide: data-auto-animate -->
## Specificity
Decides which styles are applied to an element if there are multiple overlapping ones.  
  
Hierarchy:
![Box model](/assets/img/specificity.png)

Note:
The most important thing to remember when targeting elements with selectors to apply styles is specificity.  
- A lot of people don't pay attention to it and this creates a mess further down the line, especially if other developers
need to work with this code and override something.
- It's important to build a system early on that allows for as little specificity as possible.
- Specificity follows a hierarchy.
- !important is impossible to override, unless with a more specific !important. Snowballs easily. Don't use.

--

<!-- .slide: data-auto-animate -->
## Specificity
- Think about how much specificity is needed, use as little as possible.
- Try sticking to using classes only, unless there is a reason not to.
- Try to create a system via naming or scoping where ideally every element can be targeted with a specificity of 1.
- Don't use !important.

Don't do this:
```css
#lessons .right-sidebar.lesson-sidebar div.widget-area ul.lesson-links li > a.lesson-link {
    text-decoration: none !important;
}
```

Do this:
```css
.lesson-link {
    text-decoration: none;
}
```

Note:
When working with selectors, try to remember the following suggestions
Specifity 1 is a core principle of BEM metholody, for example