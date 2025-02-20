# Cascading Style Sheets
Cascading Style Sheets (CSS) is a type of **stylesheet language** that is used to change the visual appearance of a page. CSS is by far the most widely used stylesheet language, and is relevant for any web development role. CSS is responsible for describing how HTML elements should be rendered on a screen, and is responsible for providing the rules describing how they look.

## Why use CSS?
The biggest reason to use CSS is for **separation of content and style**. When you are writing content for a web page, you don't want to have to think about how it looks. Similarly, when you're thinking of how a web page will look, you don't want to have to know the specific content that will appear on the page, although knowing the general type of content (long form, short form, images, etc.) will help make well-reasoned decisions.

Other reasons to use CSS are **reusability** and **maintainability**. If you know you want a significant vertical gap between elements in the page, rather than having to remember to add 3 or 4 `<br>` elements after each element, you can just modify the vertical spacing of your `<p>` element. This helps significantly in both reducing the effort required to make changes, as well as ensuring you don't make mistakes.

Finally, we can use CSS to help aid the **usability** of our website from an end-user perspective. The difference between a well-styled and a poorly-styled website is night and day, and good styling is very important for allowing all users to use your site.

```admonish note title="Accessibility Note"
When using CSS you should keep accessibility in mind. A common mistake made by developers is assuming that everyone has normal colour vision. With roughly 4.5% of the world's population having some form of colour blindness, it can safely be assumed that as long as your site serves more than a handful of people, you need to use colours responsibly.
```

# How to use CSS?
CSS is a single language. Regardless of how you use it, you are still writing CSS code. As the web has evolved, there are several different ways to write CSS.

## Inline CSS
Inline CSS allows you to write CSS code directly in an element. This is done using the `style` attribute of an HTML element, and provides the least amount of setup required to use CSS code. In the following example, the CSS code is written directly in the paragraph element and modifies this specific paragraph element to be different than anything else on the page.

```html
<p style="color: blue; font-size: 20px;">This text is blue and larger.</p>
```

Inline CSS is simple to use, but is **not** acceptable for use in this class, and is strongly discouraged for use elsewhere. This is because it breaks the principles we discussed earlier.

- It does not separate content and style, as you must modify the elements directly.
- It is not reusable or maintainable as you must add it to each element you want to modify.
- It significantly increases the likelihood of CSS bugs by relying on the developers to update this correctly.

## Internal CSS
Internal CSS takes the idea of being able to do CSS directly in your HTML file provided by inline CSS but it separates your concerns by bringing it to its own location within the file. This is done within the head of the file.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internal CSS Example</title>
    <style>
        p {
            color: green;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <p>This text is green and slightly larger.</p>
</body>
</html>
```

Internal CSS is better than Inline CSS, as it at least reduces the likelihood of CSS bugs. However it still requires maintaining the CSS between HTML files, and quickly grows to be unwieldy in projects larger than a few files. For this reason, Internal CSS is also not acceptable for use within this class. Some web frameworks use a form of Internal CSS, and so you may see this in the industry depending on what you work on.

## External CSS

Lastly, external CSS fully separates the CSS code from the HTML code, and we use the CSS by *linking* the two together. When we do this we must use a separate (external) file, and point our HTML file to this external file. Using the Internal CSS example above, converting this to external would involve defining two files, with the example provided below.

```admonish info
Please note that in the following example, the `href` points to `styles.css` This is a common example file name and so you'll see it a lot, especially if you use AI tools. Note that the filename could be anything. The important bit is that the `rel` attribute is defined as `stylesheet`, and the `href` attribute points to the *correctly named* file.
```

#### HTML File (index.html)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>External CSS Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <p>This text is green and slightly larger.</p>
</body>
</html>
```

#### CSS File (styles.css)
```css
p {
    color: green;
    font-size: 18px;
}
```

# Basic CSS Syntax & Structure
CSS is broken into two main components, a *selector* and a *declaration block*. The selector defines *what* you're styling, and the declaration block defines *how* you're styling it. Re-using our example from above

```css
/* The selector is p -- and selects all the paragraph elements for modification. */
p {

    /* All the code within the curly braces are declarations,
        stating how we'll modify the paragraph element. */

    color: green; /* First declaration modifies the color. */
    font-size: 18px; /* Second declaration modifies the size. */

    /* Note that each declaration is ended with a semicolon ; */
}
```

We will go into more detail on selectors in the next chapter, but the element selector described above is the most common selector you will use for now.

# CSS Properties
There are a lot of different things you can do with CSS. Each change you might want to make is done using CSS properties, and we've already discovered some through our usage so far in class. For example, the `color` property specifies the color of text within an element, and the `background-color` property specifies the color of the background.

## Properties
The following table contains a list of properties we will use in this course, as well as examples of how they can be used.
| Property            | Description                                       | Example                          |
|--------------------|-------------------------------------------------|----------------------------------|
| `color`            | Sets the text color of an element. Can use color names or other color definitions such as hex values.               | `color: blue;` or `color: #0000FF`                   |
| `background-color` | Defines the background color of an element.       | `background-color: yellow;`      |
| `font-size`        | Controls the size of the text.                     | `font-size: 16px;` or `1.2em;`   |
| `margin`          | Adds space outside an element’s border.            | `margin: 10px;` or `5% 10px;`    |
| `padding`         | Adds space inside an element’s border.             | `padding: 10px;`                 |
| `border`          | Defines a border around an element.                | `border: 2px solid black;`       |
| `width`           | Sets the width of an element.                      | `width: 200px;` or `width: 50%;` |
| `height`          | Sets the height of an element.                     | `height: 100px;` or `auto;`      |
| `text-align`      | Aligns text within an element.                     | `text-align: center;`            |

There are far too many CSS properties to provide an exhaustive list within this book. Instead, you should treat the above as a reference for what sort of properties exist. Whenever you need to use CSS properties, you should use the available resources to you on the internet to help discover what might be best for your needs. In particular, MDN Web Docs has an exhaustive [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) that can help you find CSS properties you might need to use. 

## Units 
In some of these properties, you will notice various different types of units being used. There are several different types of units, which broadly break down into **fixed** units and **relative** units. 

### Fixed Units
Fixed units are those which meet an exact specification, such as x number of pixels wide. You may use these for certain tasks, but they can cause issues with *responsiveness*, where a page does not appear correct on screens of different sizes.

| Unit  | Description | Benefits | Drawbacks |
|-------|------------|----------|-----------|
| `px` (Pixels) | Fixed unit representing exact screen pixels. Example: `font-size: 16px;` | Precise control over element sizes, consistent across devices. | Not responsive; may not scale well on different screens. |

### Relative Units
Relative units on the other hand, scale based on the definition you provide or automatically as needed. There are many different types of relative units you can use, and we will go over these in the labs.

| Unit  | Description | Benefits | Drawbacks |
|-------|------------|----------|-----------|
| `%` (Percentage) | Relative to the parent element’s size. Example: `width: 50%;` | Flexible and responsive to container size. | Can be unpredictable if parent element's size isn't clearly defined. |
| `em` | Relative to the font size of the parent element. Example: `font-size: 1.5em;` (1.5× parent’s font size) | Scales with text, useful for accessibility. | Can lead to unexpected results if nested (`em` values compound). |
| `rem` (Root EM) | Relative to the root `<html>` element’s font size. Example: `font-size: 1.5rem;` (1.5× the root font size) | Avoids compounding issues with nested elements; consistent sizing. | Still depends on the base font size (often `16px` by default). |
| `vw` (Viewport Width) | Percentage of the viewport width. Example: `width: 50vw;` (50% of the screen width) | Adapts to screen size, great for full-width layouts. | Can cause elements to shrink too much on small screens. |
| `vh` (Viewport Height) | Percentage of the viewport height. Example: `height: 100vh;` (fills the full screen height) | Useful for full-screen sections. | Can cause content to overflow on small screens. |
| `auto` | Automatically adjusts based on content and context. Example: `height: auto;` | Lets elements dynamically size based on their content. | Less predictable, may not provide precise control. |