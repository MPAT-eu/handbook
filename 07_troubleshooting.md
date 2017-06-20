## Troubleshooting

A number of issues will have been mentioned above. In these cases we will refer to the relevant chapter

### I hear the broadcast audio in the background

- The HbbTV standard has no option to automatically mute the broadcast audio. This is especially important, if you preview your application in a browser, because it has no background audio. When testing your application on a TV set, it is recommended to turn on the sound every once in a while, especially for storytelling formats, where the background sounds might be distracting
- One possible way to *mute* the broadcast audio is to add your own audio and activate *autoplay* (see Glossary &gt;&gt; Hotspots), but please be aware that
  - you will have to add an audio file for each page; This new file will play automatically when you open the new page, so there is no way (yet) to have a controlled continuous audio experience
  - If the audio is stopped by starting a new audio (see Glossary &gt;&gt; Hotspots), it will not start again when the new audio ends. The broadcast audio will be audible again.

### The editor does not accept my changes

If you use Firefox both for editing and previewing, you will have to disable FireHbbTV every time you go back to editing:

If you don't the editor may not work properly.
