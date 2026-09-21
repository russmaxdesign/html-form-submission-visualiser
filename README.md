# HTML form submission visualiser

A simple teaching tool that shows what happens when an HTML form is submitted.

The page does not send any data to a real server. Instead, it uses the browser's `FormData` API to show the data that would normally be submitted.

https://russmaxdesign.github.io/html-form-submission-visualiser/

## What this tool does

The tool contains a range of common HTML form controls.

When you fill in the form and submit it, the page shows:

* the name and value of each item that would be submitted
* a URL-encoded version of the form data
* the form method
* the form action
* which submit button was used

This makes it easier to understand how HTML forms turn user input into data.

## Key features

### Shows why `name` matters

Form controls are submitted using their `name`.

For example:

```html
<input id="full-name" name="fullName">
```

The `id` is used to connect the input to its label.

The `name` is used in the submitted data.

If a form control has no `name`, its value is not submitted.

### Shows hidden fields

The form includes a hidden input:

```html
<input type="hidden" name="recordId" value="ABC-12345">
```

The user cannot see or edit this field through the normal form interface, but its value is still submitted.

This demonstrates how hidden inputs can be used to send extra information, such as a record ID.

### Compares readonly and disabled fields

The form includes both readonly and disabled inputs.

A readonly field is submitted.

A disabled field is not submitted.

This makes the difference between these two states easy to see.

### Shows how checkboxes behave

The tool demonstrates two common checkbox patterns.

Separate yes/no questions use different names:

```text
newsletter=yes
updates=yes
```

A "tick all that apply" question uses the same name with different values:

```text
contactTime=morning
contactTime=evening
```

Unchecked checkboxes are not submitted at all.

### Shows how radio buttons work

Radio buttons in the same group share the same `name`.

For example:

```html
name="contactMethod"
```

Only the selected radio button is submitted.

If no radio button is selected, the group sends no value.

### Shows how select elements work

The form includes:

* a standard select
* a multiple select

A standard select submits one value.

A multiple select can submit the same name more than once when several options are selected.

### Shows textarea and number inputs

The form also includes common controls such as:

* textarea
* number input

Their values are included in the submitted data when they have a `name`.

### Shows that submit buttons can send data

The submit buttons also have a `name` and `value`.

For example:

```html
<button type="submit" name="action" value="save">
  Save draft
</button>
```

The button used to submit the form can add its own value to the submitted data.

### Shows what is and is not submitted

The results area includes a summary of the main rules.

Examples of things that are submitted:

* controls with a `name`
* readonly fields
* hidden inputs
* checked checkboxes
* selected radio buttons
* selected options
* the submit button that was used

Examples of things that are not submitted:

* controls with no `name`
* disabled fields
* unchecked checkboxes
* unselected radio buttons
* unselected options
* unused submit buttons
* reset buttons

## No server required

Everything runs in the browser.

JavaScript stops the normal form submission and uses `FormData` to show what the browser would have submitted.

No form data leaves the page.

## Purpose

This tool is designed to help people learn how native HTML forms work.

It is especially useful for understanding the relationship between:

* form controls
* `name`
* `value`
* submitted form data

The easiest way to learn is to change values, submit the form, and compare the results.
