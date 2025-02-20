# CSS Selectors, Attributes, and Classes

In the previous chapter, we discussed one type of selector, which is the *element selector*. This selector is the easiest to understand, as you simply select all of a certain type of element such as modifying the paragraph element color attribute with `p {color: blue;}`.

Sometimes though, you won't want to modify every single element on a page. Using this book as an example, on the left in the chapter list you see each chapter is a separate `<li>` element. Some of these elements are styled differently. Depending on which theme you have this book loaded in, you will note the inaccessible chapters are greyed out, the chapter we're on right now is highlighted, and the rest of the chapters have a default color that matches the rest of the text on the page.

~~~admonish note title="Lecture Exercise - Identifying CSS Selectors"

The chapters on the left are all using the list item `<li>` element. Using your inspector, can you identify:
1. What is unique about the currently selected page?
2. What is unique about unavailable pages?

Based on that information, how many different styles do we have defined for the list items in the navbar on the left?
~~~

## Basic Selectors

The three most common selectors used are the element selector, class selector, and ID selector.

### Element Selector

The element selector is the most basic type of selector, and is what we've seen so far. In this, you apply a generic style to all elements of a particular type. If we want to modify all h1 elements to be blue, we could use the following CSS code.

```css
h1 {
    color: blue;
}
```

### Class Selector
A *class selector* is **more specific** than an element selector. Rather than modify all of a particular element, we want to only modify elements which have a certain class. This is very powerful as it allows us to make sweeping changes to groups of elements without having to modify them individually. This is a key component of why CSS allows us to increase the reusability of our code.

Perhaps we have a site which uses paragraph tags everywhere, but we want certain types of paragraphs to be for warnings. Those paragraphs might have a class called "warning", and we can style that class differently than the rest.

The class selector is used with a period followed by the class name.

#### index.html
```html
<p> This is a regular paragraph. </p>

<p class="warning">This paragraph has the warning class associated to it.</p>
```

#### styles.css
```css
.warning {
    background-color: #FFD6D7;
}
```

### ID Selector

There are times when we want to be so specific that we need to modify a single element. In these cases, you might think that you should use inline CSS - but even in these cases you should *still* use external stylesheets for readability and maintainability.

The ID Selector is even more specific than a class selector, and refers to a specific HTML id. As you cannot have more than one element with the same id in a document, you can use these to style specific elements as needed. This is used extensively with `<div>` elements, for example when making custom content areas within a page.

The id selector is used with a hash symbol (`#`) followed by the id of the element.

#### index.html
```html
<div id="pizza-table-area">
    <!-- Code here for a table, including headings, the table itself, etc. -->
</div>
```

#### styles.css
```css
#pizza-table-area {
    background-color: red;
}

```


```admonish info title="Mixing Selectors"
It's common that a particular element on your page might match more than one selector, for example a CSS file might contain a rule for the `p` element, another rule for the `warning` class, and a rule for a specific id as well.

In this case, CSS follows the rule that has the highest *specificity*. lements are the least specific, followed by classes, and then ids are the most specific. Inline styling has the highest specificity, but you should avoid using inline styling and consider refactoring your CSS if you find yourself needing to use it to increase specificity of your CSS.

**Specificity Order (From Least Specific to Most)**

Element Selector -> Class Selector -> ID Selector -> Inline CSS
```

## Grouping Selectors

If you wish to apply the same styling to more than one element, for example modifying the colour of all headings, you can group selectors prior to the declaration block. Grouped selectors should be separated with a comma.

```css
h1, h2, h3 {
    color: red;
}
```

## More Advanced Usage
There are many additional ways to scope CSS selectors that will be useful to you as you progress through your careers.

### Attribute Selectors
You can selectively style an element based on the attribute of the element you have selected, for example styling links which include `https` in the `href`.
```css 
[href^="https"] {
    color: blue;
}
```

### Pseudo-Elements

There are several pseudo-classes and pseudo-elements you may use as well as part of a CSS selector. Pseudo in this context refers to the fact they don't actually exist as a class, or as an element on the page, but the concept is known to us. For example if you want to style a link based on when you hover over it, you can do so with `a:hover { }`. The anchor tag never actually has a `hover` class written, but your browser knows to treat an element being hovered over with your mouse as though it does.

Similarly, you can style the first or last element of within other elements using `first-child` and `last-child` such as `p:first-child { }`. Try it out!