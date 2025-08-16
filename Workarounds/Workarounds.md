**Table of contents**

1. [Turning on and off Radio buttons - Web](#turning-on-and-off-radio-buttons---web)
2. [Send HTML template body in Outlook mail through visual basic](#send-html-template-body-in-outlook-mail-through-visual-basic)
3. [Date time functionality](#date-time-functionality)
4. [Browser window focus issue](#browser-window-focus-issue)

## Turning on and off Radio buttons - Web
By default the radio button is mandatory to select so meaning you cannot unselect once done. I’ve done a workaround that helps to turn on and off like a checkbox.  This was done with external library angular material.  It is also possible to do in plain html and javascript.  Please refer to the below image for the work around.

## Send HTML template body in Outlook mail through visual basic

If for some reason you cannot view the HTML template body in the email while trying to edit.  You can open up the visual basic through the outlook search function.  Add a script to reach the HTML file and append it to the email body and view it.

## Date time functionality

The "18:30 phenomenon" typically happens when there’s an issue with time zone handling, daylight saving time, or improper conversions. Using moment-timezone and working with UTC can help mitigate most of these issues.

To work around this issue try adding 'Z' to code to see if it works. ( Converting to UTC Time formats )

## Browser window focus issue

You can use the window.parent.focus() to focus the parent window if it is behind another window. Note: This only works if the window is sub window and the sub window is opened through pop up window. ( This method doesn't work very well with all the framework.  Check official MDN documentation ).