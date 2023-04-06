# Dos and don'ts

--

## Don't use pointless wrapping elements

```html []
<p>Try to click the button</p>
<div class="button-magic">
  <div class="button-shaker">
    <button>I'm gonna fly away!</button>
  </div>
</div>
```

Note:
Wrapping a single element in a div is a common mistake.  
It works, but it complicates the HTML

In this case we have a "button-magic" which makes the button fly around the screen when the user hovers over the button.

And the "button-shaker" will shake the button when the user hover over the button.

--

## Do try to reduce nesting

```html []
<p>Try to click the button</p>
<button class="button-magic button-shaker">I'm gonna fly away!</button>
```

Note:
Instead, see if you can apply multiple classes to your main element. The end result is often the same.

--

## Don't mix different CSS patterns

```html []
<figure class="card md:flex bg-slate-100 rounded-xl p-8 md:p-0 dark:bg-slate-800">
  <img
    class="card__image w-24 h-24 md:w-48 md:h-auto md:rounded-none rounded-full mx-auto"
    src="/sarah-dayan.jpg" alt="" width="384" height="512"
  >
  <div class="card__content">
    <blockquote>
      <p class="card__description text-lg font-medium">
      ...
```

--

## Do agree with the team which pattern to use

A bad convention is better than no convention

Note:
Even if you don't agree with the team, mixing patterns will make it harder for everyone

--

## Your turn!

Share your **dos and don'ts** in the chat!
