# Hiding any page with the RED button

Pages can be specified to hide when the RED button is pressed. 

## Description

The feature is: when the option is activated and the page is shown and 
the user presses the RED button, the page disappears 
and is replaced by a short text reminder and an icon, reminding the user 
that a page is available. 

Pressing the RED button again replaces the short reminder with the page.

The short text reminder and icon stay on screen by default for 10s, and are eased out for 5mn.

## Setting the option in Page editor

At the bottom of the page editor, there is a checkbox 
labelled "Hide page with RED button". If you validate this checkbox, a text field allows you to define
the reminder message that is displayed instead of the page when the RED button has been pressed.

## Setting options in the mpat-theme

Details of on screen time and easing out and easing in and total time are located in a
script in `index.php` of the `mpat-theme`:

```javascript
var RedButtonFader = (function () {
    "use strict";
    var exports = {}, progress;
    // the Page class in the front end reads this RedButtonMode 
    // which can take as values:
    // all : all pages can be hidden by the red button
    // some : only pages with hideOnRed can be hidden by the red button (set in Page Editor)
    // none : global of the red button feature (overrides page settings)
    exports.RedButtonMode = 'all';
    exports.defaultText = 'Press RED button to show again';
    exports.resolution = 10; // 10 updates per second
    exports.durationOnScreen = 10 * exports.resolution; // 10s on screen
    exports.totalDuration = 300 * exports.resolution; // 5m total period
    exports.animationDuration = 2 * exports.resolution; // animation 2s
    exports.bottomIn = 0; // value of bottom when in
    exports.bottomOut = -30; // value of bottom when out
    exports.fade = function (div, i) {
      ...
```

In this code:
 
* `resolution` is the number of visual updates of the position per second.
* `durationOnScreen` is the number of seconds that the red button reminder stays on screen.
* `totalDuration` is the number of seconds of the complete cycle.
* `animationDuration` is the duration of the period for easing the reminder in and out.
* `RedButtonMode` is documented in the comments in the code
* `defaultText` is the text for the reminder when not defined in the page settings

The code below this fragment animates the position of the reminder from on the bottom to
30 pixels below the bottom (and not visible anymore).

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

## Tuning

* To change the frequency of the reminder, change `totalDuration` in the javascript of `index.php`
* To change the color or style of the text, change the CSS class `MPATShowOnRedTextStyle` 
in `style.css`
* To change the red square to an icon, change `background-color: red` to
`background-image: url(/path/to/image.png)` in `MPATShowOnRedIcon` in `style.css`
* To change from vertical ease in-out to horizontal, you would have to modify the script `fade`