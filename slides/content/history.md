# History

Note:
- Let's start with a bit of history, not too distant.
- Just a quick overview of what happened between HTML4 and HTML5.

---

## DOCTYPE
In HTML4
```html [1-5]
<!DOCTYPE HTML PUBLIC
  "-//W3C//DTD HTML 4.01//EN"
  "http://www.w3.org/TR/html4/strict.dtd"
>
<html>
<head>
  <title>HTML4 Example</title>
</head>
<body>...</body>
</html>
```

Note:
We had an annoyingly long DOCTYPE definition.  
Could you write that from memory?  

In this case it's a "strict" HTML4.01, which encouraged the use of CSS.  
There were also "transitional" to allow deprecated elements and attributes , "frameset" 

If you made a typo or didn't include the DOCTYPE at all newer browsers would render the page with latest standards, but IE would fall back to Quirks mode.

--

**Internet Explorer quirks mode!**  
Support everything badly!

Note:
- I'm glad that none of you have to deal with that anymore

---

## DOCTYPE
In HTML5
```html [1]
<!DOCTYPE html>
<html>
<head>
  <title>HTML5 Example</title>
</head>
<body>...</body>
</html>
```

Note:
In HTML5 it's just "DOCTYPE html"

---

<!-- .slide: data-auto-animate -->
## Language
```html [2]
<!DOCTYPE html>
<html lang="en">
<head>
  <title>HTML5 Example</title>
</head>
<body>...</body>
</html>
```

Note:
It's a good idea to define a language for your page

--

## Language

```html [2-3]
<div class="greetings">
  <div lang="en">Hello!</div>
  <div lang="et">Tere!</div>
</div>
```

Note:
But this language attribute is optional and can also be added to specific parts of your page.

---

## Inside the body
In HTML4
```html [1,3,4,9,10,11,12,13]
  <div id="header">
    <h1>Website Title</h1>
  </div>
  <div id="navigation">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
    </ul>
  </div>
  <div id="content">
    <p>This is the main content area.</p>
  </div>
  <div id="footer">Copyright 2023</div>
```

---

## Inside the body
In HTML5
```html [1,3,4,9,10,11,12,13]
  <header>
    <h1>Website Title</h1>
  </header>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
    </ul>
  </nav>
  <main>
    <article><p>This is the main content area.</p></article>
  </main>
  <footer>>Copyright 2023</footer>
```

Note:
As you can see, we now have semantically named tags for common situations.  
...which brings us to our next topic.