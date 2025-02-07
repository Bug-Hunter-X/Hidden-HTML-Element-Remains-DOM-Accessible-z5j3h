# Hidden HTML Element Remains DOM Accessible

This repository demonstrates an uncommon bug in HTML where an element, after having its content cleared and display set to 'none', remains accessible in the Document Object Model (DOM).

## Bug Description

The bug occurs when attempting to completely remove or hide an element from the DOM.  Even after setting the element's `innerHTML` to an empty string and its `style.display` property to `none`, the element persists and can be manipulated via JavaScript.  This is unexpected behavior and can lead to unexpected issues, particularly with dynamic content updates.

## How to Reproduce

1. Clone this repository.
2. Open `bug.html` in a web browser.
3. Click the "Click Me" button.
4. Observe that even though the div initially disappears, after 3 seconds it reappears with new content. This indicates that the div was still accessible in the DOM even when it appeared to be removed.

## Solution

The solution involves using `removeChild()` to remove the element entirely from the DOM instead of just clearing the content and hiding it. Refer to `bugSolution.html` for the corrected code.

## Additional Notes

This bug highlights the importance of fully understanding the differences between hiding an element (using `display: none`) and removing it from the DOM (`removeChild()`).  In many cases, removing the element is the more appropriate solution.