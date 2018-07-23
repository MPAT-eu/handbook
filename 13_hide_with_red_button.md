# Hiding any page with the RED button

Pages can be specified to hide when the RED button is pressed. 

## Description

The feature is: when the option is activated and the page is shown and the user presses the RED button, the page disappears 
and is replaced by a short text reminder and an icon, reminding the user that a page is available. 

Pressing the RED button again replaces the short reminder with the page.

## Setting the option in Page editor

At the bottom of the page editor, there is a checkbox 
labelled "Hide page with RED button". If you validate this checkbox, a text field allows you to define
the reminder message that is displayed instead of the page when the RED button has been pressed.

## Styling 

The style of the text is defined in CSS in the style.css of mpat-theme:

```css
.MPATShowOnRedTextStyle {
    color: white;
    font-family: sans-serif;
    font-size: 18px;
    position: absolute;
    bottom: 0;
    right: 0;
}

.MPATShowOnRedIcon {
    width: 20px;
    height: 20px;
    background-color: red;
    display: inline-block;
    margin-left: 5px;
}
```

This means that by default the reminder text is shown in white at the bottom right of the screen with a 20px red square.
