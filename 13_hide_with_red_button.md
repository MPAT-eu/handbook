# Hiding any page with the RED button

Pages can be specified to hide when the RED button is pressed. 

## Description

The feature is: when the option is activated and the page is shown and 
the user presses the RED button, the page disappears 
and is replaced by a short text reminder and an icon, reminding the user 
that a page is available. 

Pressing the RED button again replaces the short reminder with the page.

The short text reminder and icon stay on screen by default for 10s, and are eased out for 5mn.

## Setting the option per page in Page editor

At the bottom of the page editor, there is a checkbox 
labelled "Hide page with RED button". If you validate this checkbox, a text field allows you to define
the reminder message that is displayed instead of the page when the RED button has been pressed.

## Setting options 

Setting options is done in the Application Manager:

* Configuration: All pages / Only pages allowing it / None
* Mode: Text and icon slide in/out or fade in/out
* Direction: when in `Slide in/out` mode, you can choose the initial position of the text and icon as 
Bottom (default), Left, Right or Top.
* Duration: the total duration, defaults to 300s
* Onscreen duration: the text and icon stay on screen for that time before going, defaults to 10s 
* Outside position: when in `Slide in/out` mode, you may need to increase the sliding movement depending 
on the styles you use, e.g. margins
* Default text: the text, unless it is specified in the page by the page editor

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

.MPATShowOnRedIconLeft {
    width: 20px;
    height: 20px;
    border-radius: 10px;
    position: relative;
    bottom: -4px;
    background-color: red;
    display: inline-block;
    margin-left: 5px;
}

.MPATShowOnRedIconRight {
    width: 0;
    height: 0;
    display: inline-block;
}
```

This means that by default the reminder text is shown in white at the bottom right of the screen with a 20px red circle
to its left. You can use background-image to replace the left or right icon style with an image.

## Tuning

* To change the color or style of the text, change the CSS class `MPATShowOnRedTextStyle` 
in `style.css`
* To change the red square to an icon, change `background-color: red` to
`background-image: url(/path/to/image.png)` in `MPATShowOnRedIconLeft` in `style.css`
