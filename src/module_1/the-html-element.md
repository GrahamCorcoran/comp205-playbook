# The HTML Element

## Basic Structure
The structure of HTML is built using *elements*. In general, an HTML Element contains three components:
1. A start tag.
2. Content
3. An end tag.

```html
<h1>Hello World!</h1>
```
In the above code example, the Start tag is ``<h1>``, the content is the string "Hello World!", and the end tag is ``</h1>``.

![HTML Element](images/html-element-diagram.svg)

```admonish info title="Empty Elements"
Be aware! Not all HTML Elements have content. One example is the ``<br>`` element, which represents a line break. If an element does not have content, then it also doesn't require an end tag (as there's no need to signify the end of the content.)
```

### Not Case Sensitive
HTML Element tags are not case sensitive, meaning the following two lines of code are identical as far as HTML is concerned:

```html
<H1>I am a heading.</H1>
<h1>I am a heading</h1>
```

However, it is standard in most cases to do HTML tags in lowercase, and so we will follow that standard in this course. 

### Attributes
```admonish info
w3schools provides a fairly comprehensive [overview of element attributes](https://www.w3schools.com/html/html_attributes.asp) that doesn't go too in depth, you may find this helpful.
```

HTML Attributes provide **additional information** about elements. They are a way to provide details about how an element should be used and represented in the template. For example, with the following code representing an image:

```html
<img src="image.jpg" alt="A descriptive text">
```
the img element has two attributes. The first attribute is a src (source), which provides the file that should be placed where the image is located. The second is alt (alternative) text which displays when an image fails to load, and is also used by screen-readers and other accessibility tools to allow users who may be unable to view images to understand the content of the site.


## Nesting Elements
In HTML it's very common to nest elements into other elements. In this case, the **content** of one element may include **other elements** in addition to other things. For example, in the following code snippet:
```html
<div>
    <h1>This is a title!</h1>
    <p>This is a paragraph.</p>
    This is plain text content.
</div>
```
1. The div element contains an h1 element, a p element, and some plain text.
2. The h1 element contains plain text.
3. The p element contains plain text.

When nesting elements, ensure to indent them per the [course coding standards](../extra/coding-standards.md).