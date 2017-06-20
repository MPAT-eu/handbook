## General Information

This manual outlines and explains how to use the Multiplatform Application Toolkit: MPAT. MPAT is a WordPress-based authoring toolkit that allows easy creation and development of interactive applications for HbbTV. MPAT implements **HbbTV standards v1.0, v1.5,** and **v2.0** and supports the standard HbbTV **screen size of 1280x720 px**. Applications built with MPAT can either be viewed on a Smart TV that supports the HbbTV standard versions named above or, alternatively, MPAT can be previewed on the Firefox Internet browser using the Firefoxadd-on FireHbbTV.

MPAT supports different application designs: Classical **Website** features interlinked hierarchies of MPAT pages similar to classical websites. **SlideFlow** features a story-driven structure that follows one specific direction, promotes large imagery and video content similar to the Web-documentary style *PageFlow*. Both are closely related to the underlying navigation models (see Application Design &amp; Navigation Models for more details).

In addition to the general design of the application structure and layout, MPAT features a variety of **content components** like images, video, audio, text as well as a variety of **interactive elements** like hots spots, links, and menus among others.

**Note** : MPAT is still under development. The manual aims at describing all features that are required to build and HbbTV application with MPAT. However, the manual is work-in-progress. This affects the contents of the manual in two ways:

+ **Terminology** - Some of the labels used in the editor are still WordPress-terminology. For example, the WordPress-term *site* or *MPAT site*is used. In MPAT-terminology this would be *HbbTV app* and, hence, a *site* denotes an *HbbTV application*. See also Terminology.
+ **Scope** –The manual does not yet describe all aspects and all details of the MPAT editor tool; this is also because a couple of features that are visible in the editor are simple placeholders and have not been implemented.

### The MPAT Workflow

MPAT is a tool for journalists. Therefore, the initial idea when conceiving the editor was to split the application development process into three steps, illustrated in *Figure 1-1* :

1. The journalist develops a concept for a story. This concept serves as a basis for an HbbTV application concept. The application concept is bound to the feature set of the MPAT editor, illustrated by the *MPAT Handbook*, and can be conceived together with an MPAT application creator. In other words, based on the journalistic concept and with the help of an MPAT Handbook (which describes features and development workflows), journalists and application creators develop a concept for an interactive HbbTV application.

2. In a second step, the application creator picks up on the developed concept and turns it into a generic and empty (with no content) MPAT application, an **application model** , which can be re-used for different stories. Therefore, the application creator:
	+ chooses a **navigation model**  (Website or SlideFlow)
	+ creates a **page layout** for each page of the application.

	The page layout is an arrangement of content components per page. Content components can be populated with actual content data like video, audio, text, menus, etc.
(Side note: The creation of the application model may result in the development of new graphical layouts, technical modules or APIs that allow incorporating external sources in order to enable all envisaged features and functions.)

3. Step 3 describes the final step in the application creation process: The previously created application model is populated with actual content data. This involves creating, uploading and updating content data and as well as testing, previewing, approving and publishing the actual HbbTV application.

![MPAT Workflow](/images/workflow.png)

*Figure 1‑1*: General workflow for developing an MPAT Application in a journalistic context

### Application Design & Navigation Models

The design of HbbTV applications with MPAT is closely related to the selected navigation model. The current version of MPAT (February 2017) enables two different navigation models, **Website** and **SlideFlow**. Another model, **Timeline**, is scheduled for release in Fall 2017.

#### Website

The original idea was to use MPAT to create *simple* pages that look like traditional websites. The Navigation Model is based on buttons, clickable tiles or an overall menu. Clicking on either will lead to another page. Website allows a flexible arrangement of pages and supports user-defined navigation.

![Traditional Website - 1](/images/web_1.png)

Figure 1‑2: Traditional website design for an HbbTV application - taken from RBB's HbbTV app *verknallt &amp; abgedreht* (November 2015)

![Traditional Website - 2](/images/web_2.png)

Figure 1‑3: Simple website navigation: image tiles lead to linked pages - example from RBB's first pilot application Band Camp Berlin (2016)

#### SlideFlow

SlideFlow is the MPAT term for a very visual, very simple navigation style which resembles PowerPoint™ presentations to a large extent: full screen images, little text, occasionally interaction components or videos embedded (see screenshots below). This Navigation Model is based on the popular web format Pageflow ([http://pageflow.io](http://pageflow.io)). SlideFlow is story-based and restricts the navigation to one-directional movement in order to support the consecutive flow of pages to tell a story.

Visitors navigate this application with the Arrow Up/Arrow Down buttons on the Remote Control. Videos or interactive components are activated with the OK button and if there are more than one such component on a SlideFlow page, they have to be arranged side by side rather than above each other (see Figure 6), because Arrow Up/Arrow Down are reserved for navigating between pages.

![SlideFlow - 1](/images/slideflow_1.png)

Figure 1‑4: SlideFlow page - taken from the first RBB pilot *Band Camp Berlin*

![SlideFlow - 2](/images/slideflow_2.png)

Figure 1‑5: SlideFlow page with Audio and Video Hotspots - taken from the first RBB pilot *Band Camp Berlin* (2016)