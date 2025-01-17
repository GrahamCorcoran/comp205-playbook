# Basic Page Structure

As we've discussed already, HTML is structured in a way that makes it as easy as possible to share text-based information. Regularly, we need to display this information in a way that clearly groups different parts of the information together.

```admonish info
This is an example of an Info callout. This is an example of a set of information being displayed differently than the rest. In the case of info boxes like this, they serve as a visual highlight which can represent very important information, or information that diverges slightly from the main content of the page.

This info box is contained within a structural element called a ``<div>`` that modifies the styling of this content only to catch your eye.
```

## Structural Elements
Structural elements, or block-level elements, are elements which allow you to group elements together and modify them as a whole. For example, you may want to make all the content in the "main" area of your website centre-aligned, but keep the sidebar content left-aligned. Or perhaps you want a different background colour for your header than you do for the main body. These are all options which can be controlled by the use of structural elements.

The most common structural element, and the most generic, is the ``<div>``. 

### ``<div>`` Element
A ``<div>`` (division) element defines a separate section of an HTML document. It can be considered a container, which doesn't do anything on its own[^note] but that allows you to do things to all of the elements contained within it as a group.

A div can be styled independently, which means you can, for example, set a background colour for an entire area in your page, rather than just individual elements.

```html
<!-- Imagine we want to hide an entire section of content. Rather than add the ``hidden`` attribute to each element individually, we can wrap all of the elements in a <div>, which we can hide instead. -->
<div hidden="true">
    <h1>This is a hidden header.</h1>
    <p>This is a hidden paragraph.</p>
</div>
```

[^note]: Technically, browsers put a linebreak before and after new div by default, so I suppose you could use a ``<div>`` as an unnecessarily complex ``<br>``, but let's not.

## Semantic Structural Elements
In modern websites, there are common sections of a site that serve a similar purpose. For example, many sites (including this book!) have a sidebar that serves as a way to navigate through content quickly, especially for sites with multi-step forms, or books.

This sidebar is contained within a **semantic structural element**. In this context, semantic just means it has a specific purpose. By extension, semantic structure elements are elements which serves to group content like a ``<div>``, but in a way that is more specific to what we're trying to achieve. For example, the ``<header>`` element serves as a semantic structural element for the header of a page. Usually this contains general information about the page (such as a title), or navigational tools such as links to different sections of the site.

~~~admonish note title="Lecture Exercise - Introduction to the Inspector"

One excellent feature in Chrome is the Chrome DevTools. We will discuss this in more depth later when we discuss debugging, but one feature of the DevTools that are worth paying special attention to is the Element Inspector.

While on any webpage, you can right click and click "Inspect" (or "Inspect Element"), which will open up the ``Elements`` view of DevTools. In this view, you can see the entire HTML file that the current webpage is displaying, and all of the elements within it. 

1. In the sidebar of this book you can see links to other sections of the book.
2. Right click on the words "Course Overview", and click Inspect.
3. You will notice this opens the Elements view, and it will highlight the element you just inspected. In this case, it's an ``<a>`` element with a href to course-overview.html.
4. This element is contained within multiple nested **structural** elements. 

Can you determine which structural elements this is contained within?

Are any of the structural elements that this is contained within considered semantic structural elements? If so, which one(s)?
~~~


The following are the Semantic Structural Elements that we should be aware of for this course.

| Element        | Tag          | Purpose                                                                                                                                                                                                    |
|----------------|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header         | ``<header>`` | Almost always on the top of the page as a "strip" or "banner", serves to provide general information or navigational links.                                                                                |
| Navigation Bar | ``<nav>``    | Provides navigational links, usually on multi-page content or forms. Often on the side of a page as a sidebar, but this isn't required.                                                                    |
| Main Content   | ``<main>``   | The main content of the page. Usually the largest section, this contains the primary information the page is conveying.                                                                                    |
| Footer         | ``<footer>`` | A "strip" or "banner" of information along the bottom of the page. This usually contains information that is not intended to generally be accessed but should be available, such as copyright information. |