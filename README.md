# Uncommon HTML Bug: Incorrect innerHTML Usage

This repository demonstrates a subtle bug that can occur when manipulating the `innerHTML` property of an HTML element before the browser has fully parsed and rendered the element.  The bug arises from attempting to access and modify an element that does not yet exist in the DOM.

## The Bug

The `bug.html` file contains code that attempts to append text to a `<div>` element using `innerHTML` within a `<script>` tag placed before the `<div>` element itself.  This results in an error because the browser attempts to access an element that has not yet been added to the DOM. Therefore, the text does not append to the div successfully.

## The Solution

The `bugSolution.html` file shows the correct way to handle this situation using a conditional check. Before modifying the `innerHTML`, the code checks if the element exists using `document.getElementById('myDiv')`. If the element exists, the text is appended as expected.

## How to reproduce the bug

1. Clone this repository
2. Open `bug.html` in a web browser.
3. Observe that only the initial text("This text should be visible.") within the div is shown. The text to be appended is not displayed.
4. Then open `bugSolution.html`. The text appends successfully to the div element.