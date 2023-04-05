# Layout

---

<!-- .slide: data-auto-animate -->
## Position
Sets how an element is positioned in the document flow, and relative to what.

```css
.dog { position: static;   }
.dog { position: relative; }
.dog { position: absolute; }
.dog { position: fixed;    }
.dog { position: sticky;   }
```

--

<!-- .slide: data-auto-animate -->
## Position
```css [1]
.dog { position: static;   }
.dog { position: relative; }
.dog { position: absolute; }
.dog { position: fixed;    }
.dog { position: sticky;   }
```

- Default value for all elements.  
- Positioned normally according to the page flow.
- Top, right, bottom, left and z-index properties have no effect.

--

<!-- .slide: data-auto-animate -->
## Position
```css [2]
.dog { position: static;   }
.dog { position: relative; }
.dog { position: absolute; }
.dog { position: fixed;    }
.dog { position: sticky;   }
```

- Positioned normally according to the page flow.
- Top, right, bottom, left and z-index properties are supported.
  - Positioned relative to its default static positioning.

Note:
- Similar to static, but allows using top, right, bottom, left and z-index.

--

<!-- .slide: data-auto-animate -->
## Position
```css [3]
.dog { position: static;   }
.dog { position: relative; }
.dog { position: absolute; }
.dog { position: fixed;    }
.dog { position: sticky;   }
```

- Removed from page flow, no space allocated to it.
- Positioned relative to its closest positioned ancestor.
- Top, right, bottom, left and z-index properties are used to define its position within that ancestor.

Note:
- Used mainly to position elements on top of each other
- People often seem to have trouble using it
- Set position: relative on the parent you wish 
- Use top, right, bottom, left to position it within that ancestor, at least 2 need to be set
- Deal with overlaying

--

<!-- .slide: data-auto-animate -->
## Position
```css [4]
.dog { position: static;   }
.dog { position: relative; }
.dog { position: absolute; }
.dog { position: fixed;    }
.dog { position: sticky;   }
```

- Removed from page flow, no space allocated to it.
- Positioned relative to the viewport.
- Stays in place even when the page is scrolled.
- Top, right, bottom, left and z-index properties are used to define its position within the viewport.

Note:
- Used for creating things like sticky header etc

--

<!-- .slide: data-auto-animate -->
## Position
```css [5]
.dog { position: static;   }
.dog { position: relative; }
.dog { position: absolute; }
.dog { position: fixed;    }
.dog { position: sticky;   }
```

- Switches between relative and fixed depending on scroll position.
- Makes an element "stick" and move within a container.
- Top, right, bottom, left and z-index properties are used to define its position with the container.

Note:
- We will demonstrate this later in the workshop with a floating sidebar

---

<!-- .slide: data-auto-animate -->
## Display
The CSS property to define layouts.  
Sets how an element behaves within the container its in   
and/or how its children behave within itself.

```css
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

--

<!-- .slide: data-auto-animate -->
## Display
```css [1]
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

- Inline elements appear next to each other in a line.  
- Height and width have no effect.  
- Default example: ```<span>```.

Note:
- Mainly used when dealing with text content.  
- Vertical positioning can be tricky.  

--

<!-- .slide: data-auto-animate -->
## Display
```css [2]
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

- Block elements are each displayed on a new line. 
- They take up the full width of their container.  
- Height and width can be set manually.  
- Default example: ```<div> or <p>```.

Note:
There's also inline-block, which combines properties of both inline and block.
- Elements appear next to each other on the same line
- BUT height and width can be changed

--

<!-- .slide: data-auto-animate -->
## Display
```css [3]
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

- One-dimensional layout system.
- A flexible way to align and distribute space within a container.
- The container itself can change the width/height of its children to best fill its available space.
- Whole module with its own properties for the container & children.
- Mainly used for small-scale layouts.

Note:
- Inline and block provided a very basic way to put elements next to or under each other
- Flex gives more control of both.

--

<!-- .slide: data-auto-animate -->
## Display
```css [4]
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

- Full two-dimensional layout system.
- Whole module with its own properties for the container & children.
- Mainly used for complex large-scale layouts.
- Combines well with flex, used within its grid cells.

Note:
- The previous solutions to build grid-based systems have been hacky, finally there is a native way.
- Full support took a while, but is now at a place where its safe to use.

--

<!-- .slide: data-auto-animate -->
## Display
```css [5]
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

- Whole module with its own HTML elements and properties for its children.
- Not good at being responsive.

Note:
- Use for creating simple tables, avoid for more general layouts (use flex/grid instead)

--

<!-- .slide: data-auto-animate -->
## Display
```css [6]
.dog { display: inline; }
.dog { display: block;  }
.dog { display: flex;   }
.dog { display: grid;   }
.dog { display: table;  }
.dog { display: none;   }
```

- Completely removes the element from page flow.
  - Hidden visually.
  - Can't tab to it or its children.
  - Ignored by screen readers.

Note:
- Quick and easy way to hide something
- Be careful when using it
- Check that functionalities aren't needed
  - Screen readers, tabbing, SEO bots, layouts
  - Can't animate/transition
  - Required form element will still try to validate it

---

<!-- .slide: data-auto-animate -->
## Box model
Every HTML element is wrapped in a "box" that consists of:
- Margin
- Border
- Padding
- Content

![Box model](/assets/img/box-model.png)

--

<!-- .slide: data-auto-animate -->
## Box model
The box model allows us to:
- Define the size of an element
- Define the space between elements
- Add borders around an element

--

<!-- .slide: data-auto-animate -->
## Box model
The box-sizing property changes the way width and height are calculated.
```css
.dog { box-sizing: content-box; }
.dog { box-sizing: border-box; }
```

Notes:
- Why we are even talking about the box model, is the box-sizing property
- There are two types

--

<!-- .slide: data-auto-animate -->
## Box model
```css [1]
.dog { box-sizing: content-box; }
.dog { box-sizing: border-box; }
```

- Default behavior.
- Padding, border and margin are added to width/height values.
- Element will become larger than the defined width/height values.
- Positives:
  - Content inside is not impacted.
- Negatives:
  - Can feel unpredictable and confusing.

Notes:
- If we set an element's width to be 100px, it may not actually render to be 100px
- Harder to calculate within the bigger layout

--

<!-- .slide: data-auto-animate -->
## Box model
```css [2]
.dog { box-sizing: content-box; }
.dog { box-sizing: border-box; }
```

- Padding, border and margin are within the defined width/height values.
- Element's width/height will be exactly as defined.
- Positives:
  - Feels more predictable, easier to work with and calculate.
- Negatives:
  - Content inside might get "squeezed" or no longer fit.

Notes:
- If you set a box to be width 100px, you can be sure it will be 100px despite margin/padding
- It might be useful to just pick one and stick with it
- Mostly that's border-box, as it's easier to work with
- Most CSS resets implement this

---

<!-- .slide: data-auto-animate -->
## Layout

#### Takeaways:
- `box-sizing: border-box` everything, unless otherwise required.
- When using ```position: absolute```, make sure the ancestor you want to position it relative to 
has ```position: relative``` set on it, and at least 2 position properties (top/right/bottom/left).
- Positioning needs to be applied if you want to use z-index.
- Take the time to properly learn flex and grid, they are the most important tools for building modern layouts.
