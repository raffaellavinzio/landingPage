# Landing Page Project

## Table of Contents

- [Instructions](#instructions)
- [Implementation](#implementation)
- [Performance](#performance)

## Instructions

The starter project has some HTML and CSS styling to display a static version of the Landing Page project. You'll need to convert this project from a static project to an interactive one. This will require modifying the HTML and CSS files, but primarily the JavaScript file.

To get started, open `js/app.js` and start building out the app's functionality

For specific, detailed instructions, look at the project instructions in the Udacity Classroom.

## Implementation

Active sections and links are highlighted when scrolling.
A floating button to scroll to the top of the page becomes visible when scrolling up /down below the first screen.
The navigation bar is hidden when scrolling and reappers when not.
Smooth scrooling is enabled to each section with offset compensation for the sticky navigation bar.

## Performance

The javascript file app.js is linked in the html head section with the defer attribute on. I found multiple references on stackoverflow about this being best practice in 2019. Also, for such a short script I found that the performance is equivalent to having it linked at the bottom of the page above the body tag.

The scrolling events fire several times and this can become a problem so that techniques such a throttling and debouncing are recommended to improve performance as well explained in this [CSS tricks](https://css-tricks.com/debouncing-throttling-explained-examples/) article. I just used a rudimentary delay between events to lower their frequency, while the best approach would seem to use an ad hoc library.

I alaso used event delegation to improve performance and add a single click event at the navigation bar level to bubble up all the individual link clicks.

In matter of styling I kept separtion of concerns by using classList methods only to change CSS rules and used the hide/change/show strategy for the button up and the navbar visibility to avoid reflow and leverage repaint only processing.
