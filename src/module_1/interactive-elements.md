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
Another way of adding information is a select box, which is used when you know the different options a user could choose. Selects are very helpful for ensuring data integrity, by preventing the user from submitting anything except for the pre-determined information you'd like them to.

```html
<select id="pizza" name="pizza">
  <option value="veggie">Vegetarian</option>
  <option value="canadian">Canadian</option>
  <option value="meat">Meat</option>
  <option value="cheese">Cheese</option>
</select>
```
On this page, this select is rendered like so:
<select id="pizza" name="pizza">
  <option value="veggie">Vegetarian</option>
  <option value="canadian">Canadian</option>
  <option value="meat">Meat</option>
  <option value="cheese">Cheese</option>
</select>

Note, this book contains custom CSS so a default select will look different without styling.