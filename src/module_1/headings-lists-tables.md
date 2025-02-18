# Introduction to Specific Elements
So far, we have discussed many different forms of text-based elements where the purpose of the element was to display or modify text in some way, such as paragraph elements and heading elements. We've also learned about how to use divisions to "section off" multiple elements at the same time, for example to hide many elements at once.

Some elements have specific meanings and purposes, and you should be aware of them and how to use them. In this section, we'll discuss *lists*, *media*, and *tables*. In the next section, we will discuss *forms* and how basic interactivity can be achieved using them.

## Lists
Lists allow you to group sets of related items or information together. For example, you can use a bulleted list to express point-form ideas. You can use a numbered list to express how to achieve something in a step-by-step way.

In HTML this is accomplished using two types of lists, unordered lists and ordered lists. By default, HTML will use basic bullet points for unordered lists, and numerical bullets incrementing from 1 for ordered lists.

### Unordered Lists
Unordered lists are lists where the items do not have any ordering associated to them. They are commonly identified using bullets. An example in real life is a grocery list, if you need to get eggs, milk and sugar to bake a cake -- the order you get those items in is irrelevant. You need all three in order to bake a cake, in any order.

To create an unordered list, we use two tags: ``ul`` to define the list itself, and ``li`` for each item contained within the list. Using our shopping list example, an unordered list of our items.
```html
<p>To bake a cake, we need:
    <ul>
        <li>Eggs</li>
        <li>Milk</li>
        <li>Sugar</li>
    </ul>
</p>
```

### Ordered Lists
Ordered lists, on the other hand, are for when the ordering of your list items *does* matter. If we extend the analogy for the cake, in the process of baking you have to do things in a certain order or your cake will not turn out. It's not possible to bake the cake first, then mix the milk and flour together.

```html
<p>With your eggs, milk, and sugar, you should:
    <ol>
        <li>Mix everything together</li>
        <li>Place in a cake tin</li>
        <li>Bake</li>
    </ol>
</p>
```

## Media

Often you will want to share non-text media on a webpage, and this is typically achieved by using specific tags for each media type.

### Images
Images are added to a page using the ``<img>`` tag. This tag has a required attribute, ``src`` which specifies the location of the file. This file can be local to your filesystem, or can be an external link to a file hosted on the web. 

There is also an ``alt`` attribute which specifies the text provided when an image fails to load, or provided to screen-readers to describe an image. While not required by HTML, this should always be provided for accessibility reasons.

```html
<img src='cat.png' alt="A cat sleeping on a jacket.">
```

### Sound
Similarly, the ``<audio>`` element allows you to play audio files directly in the browser. This element commonly uses the ``controls`` attribute, which adds audio controls to the browser directly. Within the content area of the ``<audio>`` element, you must add ``<source>`` elements which provide audio files to be used by the browser. For example, if we have an audio recording of a cat meowing, our HTML might look like this:

```html
<audio controls>
    <source src="meow.ogg" type="audio/ogg">
    <source src="meow.mp3" type="audio/mpeg">
</audio>
```

### Videos
Finally, the ``<video>`` element provides the ability to play videos. Like the ``<audio>`` element, you may provide a ``controls`` attribute to enable the ability to control the media playback. Additionally, you should specify ``width`` and ``height`` attributes to ensure the video is reasonably-sized.

You may also provide text within the content area of the ``<video>`` element, and that text will only be rendered if the video player is not able to be rendered.

```html
<video width="480" height="320" controls>
    <source src="cat.mp4" type="video/mp4">
    This text is only displayed if the browser cannot render the video element.
</video>
```

## Tables

A table is a common way to display data that is multi-dimensional, or sometimes to display data where a list would be too cumbersome. Tables are created using four elements:
- ``<table>`` - the main table element which specifies the entire table.
- ``<tr>`` - the table row element, which creates a new row.
- ``<td>`` - the table data element which specifies a cell within a row.
- ``<th>`` - the table header eleemnt, which you use instead of ``<td>`` for header information, rather than data.

By default, the ``<th>`` element bolds and centers the headers of a table. This can be modified through CSS.

A basic table representing products for sale might be:

```html
<table>
    <tr>
        <th>Product Code</th>
        <th>Product</th>
        <th>Price</th>
    </tr>
    <tr>
        <td>APP13</td>
        <td>Apples (kg)</td>
        <td>$4.00</td>
    </tr>
    <tr>
        <td>B4N4N4</td>
        <td>Bananas (kg)</td>
        <td>$3.00</td>
    </tr>
</table>
```
