# Forms

When you are collecting user-submitted information, you need to be able to send this to a server somehow. This is often done by using HTML Forms. A form is simple: it's a container that holds information that will be submitted to a server. At the core, a form is just an element with other nested elements contained within it.

```html
<form>
    <input type="text">
    <input type="checkbox">
    <input type="submit">
</form>
```

## Input Element

In order to collect information, HTML Forms include ``<input>`` elements, which allows the user to input information in different formats. This element includes several attributes which are useful to us for defining the data that gets submitted.

Several input types we will use include:

| Input Type | Description                                                    | Usages                                                                                        |
|------------|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| text       | A text field for user-submitted text.                          | Any time you should receive text from a user, such as gathering their name for a pizza order. |
| password   | A text field for user-submitted text where the text is hidden. | Passwords or other sensitive information.                                                     |
| checkbox   | A multi-select of options that will be sent together.          | Anywhere multiple options are valid, such as pizza toppings.                                  |
| radio      | Like a checkbox, except only one option is valid.              | Type of crust, since your pizza can't be both thin and thick crust.                           |
| date       | A date picker.                                                 | To pick dates.                                                                                |
| submit     | A button to submit a form.                                     | Most forms include a submit button unless they rely on JavaScript to do something unique.     |

For a complete list of ``<input>`` types, see [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types).

## Select Element
The first way to add information we will discuss which you are already familiar with from your day-to-day life is a select box, which is used when you know the different options a user could choose. Selects are very helpful for ensuring data integrity, by preventing the user from submitting anything except for the pre-determined information you'd like them to.

```html
<select id="pizza" name="pizza">
  <option value="veggie">Vegetarian</option>
  <option value="canadian">Canadian</option>
  <option value="meat">Meat</option>
  <option value="cheese">Cheese</option>
</select>
```
On this page, this select is rendered[^note] like so:
<select id="pizza" name="pizza">
  <option value="veggie">Vegetarian</option>
  <option value="canadian">Canadian</option>
  <option value="meat">Meat</option>
  <option value="cheese">Cheese</option>
</select> 

In this code, we introduce the `value` and `name` attributes. These attributes work together to allow the `select` to build data that can be sent to the back end server that the form is submitting to. For example, in the above example you can imagine the following data gets sent to a server when you select the `veggie` option.

```json
{
  "pizza": "veggie"
}
```

If you selected the `canadian` option instead, the name would be the same, but the `value` would be different. This is very helpful when combined with more complicated forms to ensure you can parse the information that is being sent to you.

```json
{
  "pizza": "canadian"
}
```
[^note]: Since this book contains custom CSS, a default select will look different without styling.


## Label Element
When creating forms, we can use labels to associate text directly to an input. Beyond just using a generic text element, this achieves more by being programmatically linked to the input. This helps us in a few ways:
- We are able to trust that screen readers and other accessibility tools will be able to parse information about our inputs.
- It increases the physical area of the form inputs, meaning it's easier to select, especially on a mobile device where you use touch controls.

Labels use the `for` attribute to specify the `id` of the element which they are labelling. For example, given our pizza selector above, we might use the following label:

```html
<label for="pizza">Select your pizza:</label>
<select id="pizza" name="pizza">
  <option value="veggie">Vegetarian</option>
  <option value="canadian">Canadian</option>
  <option value="meat">Meat</option>
  <option value="cheese">Cheese</option>
</select>
```