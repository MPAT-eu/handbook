## Terminology

This glossary aims to explain the necessary terms and functions:

| Term | Definition |
|---|---|
| Application | An application consists of *a)* 1-n pages, *b)* is based on a Scenario and *c)* follows a Navigation Model |
| Component | A component is also referred to as content type and defines certain functionality that can be added to a page based on the selected Page Layout. For instance, a component can be an image canvas or image gallery, a video player, or a text field. |
| Focus | In contrast to websites on a PC, you don’t navigate with a pointer device (e.g. a mouse) or your fingers on the touchscreen. In an HbbTV application you navigate with the arrow keys of your Remote Control. The point (menu button, component) where you currently are has the Focus. As a visual orientation it is recommended that the active component has a border to give the user some visual orientation. Borders (for active links, etc.) are defined globally. |
| Hot Spot | In MPAT, a Hot Spot is a component which activates content indirectly. E.g. if you want to play an audio or a video without a player canvas, you would put a Hot Spot (see Figure 5). The Hot Spot is a media icon (currently text, audio or video) which changes its colour when it is in focus and changes its state when it is activated (in Figure 5, the audio is active, i.e. in Focus and playing; use your arrow keys to navigate to the video Hot Spots, press OK to start the video.) |
| Navigation Model | The Navigation Model defines how the user navigates between the pages of an application. Every application can only have one Navigation Model. It is possible, though, to interlink between applications so that, from a consumer perspective, an application may seem to follow different Navigation Models (in different areas of a service). The MPAT Navigation Models available to date (Website, SlideFlow, Timeline) are described in chapter 1.2. |
| Page | Every application consists of 1-n Pages. The Content Creator decides on the number, order and the content of the pages. |
| Page Layout | Every page of an application is based on a Page Layout. Page Layouts are created and edited in their own WordPress category. A Page Layout defines the positioning of boxes, not which modules will appear in these boxes - usually the App Creator will foresee a certain component for each box, but it is the Content Editor’s choice what s/he wants to put there. |
| Page Model | Model of a page |
| Scenario | A Scenario describes what users can do using an application. This can be a concrete description of an actual application or a more generic description of what people could do. |
| Site | In the MPAT-Editor each site represents a full HbbTV application. To avoid ambiguities, the term "website" should be replaced with "HbbTV Site" or “MP Application” (a Multi-Platform Application which is built with the Multi-Platform Application Toolkit, MPAT). |
| Template | What we called “Template” in D2.1 is now a “Page Layout” in WordPress |
| Use Case | A Use Case describes a certain functionality in a scenario, such as “Voting” or “Connect Second Device”. Typically, a scenario will consist of multiple use cases. |
