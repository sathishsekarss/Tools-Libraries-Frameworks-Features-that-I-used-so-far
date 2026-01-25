**Table of contents**

1. [Turning on and off Radio buttons - Web](#turning-on-and-off-radio-buttons---web)
2. [Send HTML template body in Outlook mail through visual basic](#send-html-template-body-in-outlook-mail-through-visual-basic)
3. [Date time functionality](#date-time-functionality)
4. [Browser window focus issue](#browser-window-focus-issue)
5. [Checkbox tree multiple nested checkbox](#checkbox-tree-multiple-nested-checkbox)

## Turning on and off Radio buttons - Web
By default the radio button is mandatory to select so meaning you cannot unselect once done. I’ve done a workaround that helps to turn on and off like a checkbox.  This was done with external library angular material.  It is also possible to do in plain html and javascript.  Please refer to the below image for the work around.

## Send HTML template body in Outlook mail through visual basic

If for some reason you cannot view the HTML template body in the email while trying to edit.  You can open up the visual basic through the outlook search function.  Add a script to reach the HTML file and append it to the email body and view it.

## Date time functionality

The "18:30 phenomenon" typically happens when there’s an issue with time zone handling, daylight saving time, or improper conversions. Using moment-timezone and working with UTC can help mitigate most of these issues.

To work around this issue try adding 'Z' to code to see if it works. ( Converting to UTC Time formats )

## Browser window focus issue

You can use the window.parent.focus() to focus the parent window if it is behind another window. Note: This only works if the window is sub window and the sub window is opened through pop up window. ( This method doesn't work very well with all the framework.  Check official MDN documentation ).

## checkbox tree multiple nested checkbox
You can use recursive function to handle multiple nested checkbox tree structure.  Each time a parent checkbox is selected or unselected, the child checkboxes will also be selected or unselected accordingly.  You can also implement indeterminate state for parent checkboxes when some but not all child checkboxes are selected.  This was done using angular material tree component.
Faced issue while implementing this feature where the indeterminate state was not updating correctly.  Resolved it by ensuring that the state of parent checkboxes is recalculated whenever a child checkbox is toggled.

Key points to remember:
- Use recursive functions to traverse the tree structure.
- Update the state of parent checkboxes based on the state of their child checkboxes.

Smart fixes done are:
Handing checkbox event and click event separately to avoid event propagation issues.