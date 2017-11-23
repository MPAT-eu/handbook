# TimeLine

The TimeLine navigation model was designed to allow triggering of the appearance and 
disappearance of many pages on top of a video, based on various kinds of time/events.
As pages appear on top of a video, their background should be transparent.
The pages in a TimeLine are plain MPAT pages, see the WebSite navigation model and the
rest of this handbook for information on how to create and edit them.

In order to use the timeline editor, you have to select the TimeLine navigation model in the
MPAT Application Settings. Then the watch icon of the TimeLine editor appears in the left sidebar menu.

## TimeLine Editor

Here is the aspect of the TimeLine editor:

![TimeLine editor](/images/timelineeditor.png)

The top left large rectangle is the preview area, with a standard TV background as default image.
In this preview area, the current page is shown.

The line below is the time line with:

* a zone to display events
* a scale below
* a red thin marker to indicate the current time in the preview area

The Event Editing box below allows manual editing of events.

At the bottom left, a button allows changing the list of events that can be added.

To the right of that button, the current application URL is displayed.

In the right sidebar:

* The RESET button resets the timeline, removing all the exiting events and video in the back.
* The RESTORE button restore the previous saved timeline.
* The SAVE button saves the current timeline (events and video).
* The Timeline box allow the editing of the timeline duration, specified in seconds.
* The Add to the timeline box allows the addition of 
  * A video page if a on-demand video is intended
  * Any kind of event
  * The Target page selector allows the selection of the 
page pointed by the event to be added: the page to be added can be an existing page, or <empty>
when you want the next event to remove the current page.
  * The Add element button adds an element of the selected type to the timeline
* The Streamevent container allows the specification of the streamevent characteristics,
see the HbbTV standard.
* The BeeBeeBox allows the creation of an XML descriptor for use with a beebeebox when
debugging a timeline application.

## Events

Events cannot overlap in the timeline. To change the order of events in the timeline, 
you can swap two events. Select the event on the left of the pair, and press "SWAP SELECTED"

Media Events and Time Events have a meaningful duration. Their duration can be changed by dragging
the handle on the right.

Other events have a constant width that has no meaning in time. The width is only useful
to be able to edit those events, select them, move them by dragging. Because this width
is small, the background color of the event is extended to the right of the event, with a gradient.
The title of the page referred by the event is displayed on that fading background.

![Events](/images/events.png)


## Howtos

### How to add an event

1. In the Add to the timeline box on the right, choose a type of event
1. Choose a Target Page, which can be an existing page or <empty> if you want the event
to remove the currently displayed page
1. Select the event to the left of the zone in which you want the new event to be inserted.
1. Press "ADD ELEMENT"

The event is then added to the right of the currently selected event, or the first free zone from the left.

Stream Events are DVB StreamEvents. They do not have a meaningful width/duration. 
Their apparent width is just to make them visible and selectable.
They have a data value: in the timeline application, when a DVB StreamEvent is received,
its data field is compared to the data value, and if it matches, the page referred
by the Stream Event is shown.

Media Events are connected to the time of the on-demand video in the back, if there
is one. Media Events have a start time and a duration. The page that a Media Event
refers to is shown at the beginning and hidden at the end.

Time Events are connected to the time since the HbbTV application started. They otherwise 
behave like Media Events.

Clock Events are events triggered on a UTC time. They do not have a meaningful width/duration. 
Their apparent width is just to make them visible and selectable.

Key Events are events triggered by pressing a key on the remote control.
They do not have a meaningful width/duration. 
Their apparent width is just to make them visible and selectable.
They have a KeyCode such as "RED", "GREEN", "BLUE", "YELLOW", "ENTER", "UP"...

The display time of Key Events, Stream Events and Clock Events is artificial and only
useful to edit them or test the preview.

### How to test the preview

1. Select the thin red vertical bar on the timeline and drag it to the wished preview time.

### How to remove an event

1. Select the event in the time line
1. Press the button "REMOVE SELECTED" in the Event Editing box

### How to move an event / change its start time

There are multiple ways:

1. Drag the event left or right in the time line. OR
2. Select the event and change the Begin value in the Event Editing box

### How to change the duration of an event

Media Events and Time Events have a meaningful duration. The page they refer to is 
shown at the beginning of the time interval and is hidden at the end. There are two
ways of changing the duration of the event:

1. Drag the white > on a black background at the right of the event. OR
1. Select the event and edit the duration field in the Event Editing box.

## TimeLine Wizard

The first time you access the timeline editor, you get this screen:

![TimeLine wizard](/images/timelinewizard.png)

The text of the wizard is explicit. The principle is that you can choose between
a standard broadcast editor with just Stream Events, a standard VOD editor with
just Media Events, or any variant of the two with more events. Click on the arrow at 
the bottom to exit the wizard and start editing.

