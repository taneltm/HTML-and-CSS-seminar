# HTML Forms

Note:
Let's quickly go over some of the more advanced cases of HTML forms

---

## A typical form
```html []
<form action="subscribe.php" method="post">
  <div>
    <label for="name">Enter your name: </label>
    <input type="text" name="name" id="name" required>
  </div>
  <div>
    <label for="email">Enter your email: </label>
    <input type="email" name="email" id="email" required>
  </div>
  <input type="submit" value="Subscribe!">
</form>
```

Note:
- The form action and methods...
- Labels and inputs are linked by the input's ID and the label's for attribute
- Clicking a submit button triggers the "submit" event

--

## Text validation
```html
<input
  type="text"
  pattern="[A-Za-z]{3}"
  required
>
```

Note:
- Form submission will be denied if validation fails.  
- Browsers can show a validation warning tooltip

--

## Type and constraints
```html
<input type="number" min="0" max="10" step="2">
<input type="email">
<input type="color">
...
```

Note:
- Some input types have built in validation.
- Some of the browser's native controls will limit what you can choose.

--

## Get the correct data type
```html []
<input type="date">
<input type="number">
```

```js []
const str = document.querySelector('input[type="date"]').valueAsDate
const num = document.querySelector('input[type="number"]').valueAsNumber
```

Note:
- For the date and number inputs, you don't need to convert the textual value to a date object or number

--

## Check inputs for validity
```js [3,4,7]
const input = document.getElementById("language")

if (!input.validity.valid) {
  if (input.validity.valueMissing)
    console.error("No value")

  if (input.validity.patternMismatch)
    console.error("Wrong value")

}
```

Note:
- You can also check what went wrong with JavaScript

