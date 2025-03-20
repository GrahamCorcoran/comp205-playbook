# Events Overview

## What are DOM Events?
DOM (Document Object Model) events are actions or occurrences that happen in the browser, which can be detected and responded to using JavaScript. Events allow developers to create dynamic, interactive web applications by responding to user interactions or browser actions.

When you do pretty much anything on a web browser, you're triggering events all the time. The web page can then capture and handle these events and do things with them. For example, if you've ever seen a webpage which does a fancy animation when scrolling, they have captured and overridden the ``scroll`` event!

## Event Handling Methods
There are two main ways to handle events in JavaScript:

### HTML Event Attributes

For HTML events where this is supported, you can edit the attribute directly, such as in the below code.

```html
<button onclick="alert('Clicked!')">Click Me</button>
```

### Event Listeners in JavaScript
Instead of editing the HTML event directly, we can separate our concerns by using event listeners in JavaScript. This is the preferred method for this course.

```js
const btn = document.querySelector('button');
btn.addEventListener('click', () => {
    console.log('Button clicked!');
});
```

## Common Types of DOM Events

### 1. Mouse Events
Triggered by mouse actions such as clicks, movement, or hovering.
- `click`: Fires when an element is clicked.
- `dblclick`: Fires when an element is double-clicked.
- `mouseover`: Fires when the mouse enters an element.

### 2. Keyboard Events
Triggered when the user interacts with the keyboard.
- `keydown`: Fires when a key is pressed down.
- `keyup`: Fires when a key is released.

### 3. Form Events
Triggered by interactions with form elements.
- `submit`: Fires when a form is submitted.
- `change`: Fires when an input value changes (after losing focus).
- `input`: Fires when the value of an input changes (in real-time).
- `focus`: Fires when an element gains focus.
- `blur`: Fires when an element loses focus.

### 4. Window Events
Triggered by actions on the browser window.
- `load`: Fires when the whole page (including all resources) is loaded.
- `resize`: Fires when the window is resized.
- `scroll`: Fires when the page is scrolled.

### 5. Clipboard Events
Triggered when users copy, cut, or paste content.
- `copy`: Fires when content is copied.
- `cut`: Fires when content is cut.
- `paste`: Fires when content is pasted.