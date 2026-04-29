# Workarounds and Fixes
The below are some of the workarounds and fixes that I have implemented while working on various projects.  These solutions address common issues and challenges faced during development.  These does not cover all the issues faced but only the prominent ones that I could remember.

**Table of contents**

🛠️ - Fixes
💡 - Ideas

1. [Turning on and off Radio buttons - Web 🛠️](#turning-on-and-off-radio-buttons---web)
2. [Send HTML template body in Outlook mail through visual basic 🛠️](#send-html-template-body-in-outlook-mail-through-visual-basic)
3. [Date time functionality 🛠️](#date-time-functionality)
4. [Browser window focus issue 🛠️](#browser-window-focus-issue)
5. [Checkbox tree multiple nested checkbox 🛠️](#checkbox-tree-multiple-nested-checkbox)
6. [Chatbot 💡](#chatbot)
7. [Selected filter counter 💡](#selected-filter-counter)
8. [Parsing multiple lines in textarea input when copied from excel 🛠️](#parsing-multiple-lines-in-textarea-input-when-copied-from-excel)
9. [Spring batch application to process large volume of data separately 🛠️](#spring-batch-application-to-process-large-volume-of-data-separately)
10. [ngx-infinite-scroll issue 🛠️](#ngx-infinite-scroll-issue)
10. [menu options should be visible on hovering over 🛠️]](#menu-options-to-be-visible-on-hovering-over)

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

## Chatbot
Implemented smart suggesion feature.  It sends the api request silently in the background while the user is typing.  Once the user stops typing for a few milliseconds, the latest request response is shown as suggestions.

This smart suggestion was implemented for every page using the angular router.  Whenever the route changes, the chatbot component is re-initialized to ensure it works seamlessly across different pages.

## Selected filter counter
Implemented a selected filter counter that dynamically updates based on the number of active filters applied by the user.  This counter provides real-time feedback to users about how many filters are currently in effect, enhancing the user experience.  Implmeneted this feature using angular ngrx state management to efficiently track and update the count of selected filters across different components from the API request.

## Parsing multiple lines in textarea input when copied from excel
When users copy data from Excel and paste it into a textarea, the data often contains multiple lines.  To handle this, I implemented a parsing function that splits the input based on newline characters and processes each line accordingly.

The regex used for splitting the input is:
```javascript
const lines = input.split(/\r?\n/);
```

## Spring batch application to process large volume of data separately
When dealing with large volumes of data, processing it in a single batch can lead to performance issues.  To address this, I implemented a Spring Batch application that processes data in smaller chunks.  This allows for better resource management and improved performance. The application can be configured through Cron jobs to run at specific intervals, ensuring that data is processed efficiently without overwhelming the system.

## ngx-infinite-scroll issue
Implemented ngx-infinite-scroll in an Angular application to load more data as the user scrolls down.  By importing the InfiniteScrollModule and adding the necessary event handlers, I was able to fetch additional data when the user reaches the bottom of the page.  This enhances the user experience by providing a seamless way to access more content without needing to click on pagination links.  On reaching the bottom of the page, the onScroll() method is triggered, which can be used to make an API call to fetch more data and append it to the existing list with Page number and page size parameters passed to the API request.  This implementation allows for efficient data loading and improved performance, especially when dealing with large datasets.

## menu-options-to-be-visible-on-hovering-over
When using angular material mat menu it is not possible to use the hover options for button to show the menu options.  Since angular uses overlay, it causes lot of issues.  The best work around I did is use plain html and CSS show the menu options when hovering over.
