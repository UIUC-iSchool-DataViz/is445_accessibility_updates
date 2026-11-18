---
layout: default
title: Accessibility
description: Accessibility statement and WCAG 2.1 conformance report for the course website
---

{% assign co = site.data.class.course %}
{% assign ii = site.data.class.instructor %}
{% assign course_webpage = site.url | append: site.baseurl %}
{% assign src = "https://github.com/" | append: site.githuburlbase | append: site.baseurl | append: "/blob/main/" %}
{% assign tree = "https://github.com/" | append: site.githuburlbase | append: site.baseurl | append: "/tree/main/" %}
{% assign course_github = "https://github.com/" | append: site.githuburlbase | append: site.baseurl %}

This is the report for the course website. See also the
[accessibility overview]({{ '/accessibility_home' | relative_url }}) and the
[report for the course's PrairieLearn content]({{ '/accessibility_pl' | relative_url }}).

## Accessibility Statement

We want every student in {{ co.number }} ({{ co.name }}) to be able to use the course
materials. This page documents how the course website currently measures up against the
[Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/) at Levels A
and AA, including the places where it falls short. We are actively working through the
known issues listed below.

If any part of this website is a barrier for you, please contact the instructor at
[{{ ii.email }}](mailto:{{ ii.email }}). You do not need to wait for a fix to be published:
we will provide the material in a format that works for you. Students who need
accessibility-related academic adjustments should also see the
[Accessibility Statement in the syllabus]({{ '/syllabus' | relative_url }}#accessibility-statement)
and contact [Disability Resources and Educational Services (DRES)](http://disability.illinois.edu).

## Conformance Report

This report follows the structure of the
[VPAT® 2.4Rev WCAG edition](https://www.itic.org/policy/accessibility/vpat).

| | |
|---|---|
| **Name of product** | {{ co.number }} {{ co.name }} course website |
| **Location** | [{{ course_webpage }}]({{ course_webpage }}/) (source: [{{ course_github }}]({{ course_github }})) |
| **Report date** | November 2026 |
| **Description** | A static website, built with Jekyll and hosted on GitHub Pages, that publishes the course syllabus, weekly overview pages, lecture slides, and Jupyter notebooks. |
| **Contact** | {{ ii.name }}, [{{ ii.email }}](mailto:{{ ii.email }}) |
| **Standard** | [WCAG 2.1](https://www.w3.org/TR/WCAG21/) Level A and Level AA |

### Scope

The report covers the four kinds of page that make up this website:

- **Regular pages**: the home page, the syllabus, and the weekly overview pages.
- **Lecture slides**: slide decks written in Markdown and displayed in the browser with
  [reveal.js](https://revealjs.com/) 4.0.2.
- **Notebook viewer**: Jupyter notebooks displayed in the browser with
  [nbviewer.js](https://github.com/kokes/nbviewer.js).
- **Downloadable files**: notebooks, Python files, data files, and one PDF.

The report does not cover the separate platforms the course links to (Canvas, PrairieLearn,
Slack, GitHub, YouTube, and Vimeo) or other external websites. Each of those is responsible
for its own accessibility; where one is available, please see that platform's own
accessibility documentation, for example
[PrairieLearn's conformance report](https://www.prairielearn.com/accessibility).

### Evaluation methods

This evaluation was a manual review of the website's source code: the page templates, the
style sheets, the Markdown source of the 26 published slide decks, and the notebook viewer
page. Counts of images, videos, and similar items quoted in the remarks come from that
source. Colour contrast was calculated from the colour values in the style sheets.

The following have **not** yet been done, and ratings may change once they are:

- testing with a screen reader (such as VoiceOver, NVDA, or JAWS);
- hands-on keyboard-only testing in a browser;
- a scan with an automated checker (such as axe or WAVE);
- a review of caption quality on the embedded third-party videos;
- a review of each individual image, chart, animated GIF, and notebook output.

### Terms

The terms used in the "Conformance level" column are defined as follows:

- **Supports**: the functionality of the website has at least one method that meets the
  criterion without known defects, or meets it with equivalent facilitation.
- **Partially Supports**: some functionality of the website does not meet the criterion.
- **Does Not Support**: the majority of the website's functionality does not meet the
  criterion.
- **Not Applicable**: the criterion is not relevant to the website.

### Status

The "Status" column in each table tracks our progress on that criterion. Each entry lists
the files to look at, linked to the course's GitHub repository.

{% include a11y_legend.html %}

### Table 1: Success Criteria, Level A

| Criteria | Conformance level | Remarks and explanations | Status |
|---|---|---|---|
| [1.1.1 Non-text Content](https://www.w3.org/TR/WCAG21/#non-text-content) | Partially Supports | Many slide images have descriptive alternative text, but about 3 in 10 do not: of 344 inline images in the 26 published slide decks, 84 have no alternative text and 19 more use the placeholder "drawing". A further 71 slides show an image only as a slide background, which cannot carry alternative text. On regular pages, the weekly illustration images have no alternative text, including the ones on the home page that are links. Charts and images inside notebook outputs have no alternative text. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): add alt text to each image</a></li><li><a href="{{ src }}_layouts/index.html"><code>_layouts/index.html</code></a>: add alt text to the weekly illustration links</li><li><a href="{{ src }}_layouts/week.html"><code>_layouts/week.html</code></a>: mark the illustration as decorative (empty alt)</li><li><a href="{{ tree }}week01/"><code>week01/</code></a>: notebooks in each week folder (*.ipynb): describe output charts</li></ul>{:/} |
| [1.2.1 Audio-only and Video-only (Prerecorded)](https://www.w3.org/TR/WCAG21/#audio-only-and-video-only-prerecorded) | Partially Supports | The website hosts no audio-only content. Slides include animated GIFs (61 GIF files in the repository), which are silent video-like content; many have no text description. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): "GIFs" column; describe each animation</a></li></ul>{:/} |
| [1.2.2 Captions (Prerecorded)](https://www.w3.org/TR/WCAG21/#captions-prerecorded) | Partially Supports | The website hosts no video files of its own. Slides embed nine third-party videos from YouTube and Vimeo. Captions depend on each video's publisher and have not yet been checked. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ src }}week06/lecture06.md"><code>week06/lecture06.md</code></a>: check captions on each embedded video</li><li><a href="{{ src }}week07/lecture07p2.md"><code>week07/lecture07p2.md</code></a>: check captions on each embedded video</li><li><a href="{{ src }}week10/lecture11p2.md"><code>week10/lecture11p2.md</code></a>: check captions on each embedded video</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: check captions on each embedded video</li></ul>{:/} |
| [1.2.3 Audio Description or Media Alternative (Prerecorded)](https://www.w3.org/TR/WCAG21/#audio-description-or-media-alternative-prerecorded) | Partially Supports | The embedded third-party videos are not known to have audio description, and the slides do not provide text alternatives for them. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}week06/lecture06.md"><code>week06/lecture06.md</code></a>: add a text summary or described version of each video</li><li><a href="{{ src }}week07/lecture07p2.md"><code>week07/lecture07p2.md</code></a>: add a text summary or described version of each video</li><li><a href="{{ src }}week10/lecture11p2.md"><code>week10/lecture11p2.md</code></a>: add a text summary or described version of each video</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: add a text summary or described version of each video</li></ul>{:/} |
| [1.3.1 Info and Relationships](https://www.w3.org/TR/WCAG21/#info-and-relationships) | Partially Supports | Regular pages use page regions (header, navigation, main, footer), headings, and lists, and Markdown data tables have header cells. Exceptions: the course information block at the top of the syllabus uses a table for layout and contains incorrectly nested lists; the syllabus skips heading levels in places; and some slides use tables without header cells to place images side by side. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_includes/class_info.html"><code>_includes/class_info.html</code></a>: replace layout table; fix nested lists</li><li><a href="{{ src }}syllabus.md"><code>syllabus.md</code></a>: fix skipped heading levels</li><li><a href="{{ src }}week03/lecture03p2.md"><code>week03/lecture03p2.md</code></a>: layout tables</li><li><a href="{{ src }}week08/lecture08p1.md"><code>week08/lecture08p1.md</code></a>: layout tables</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: layout tables</li></ul>{:/} |
| [1.3.2 Meaningful Sequence](https://www.w3.org/TR/WCAG21/#meaningful-sequence) | Supports | Content is written in reading order in the page source. Some slides use two-column layouts, but the source order matches the visual order. Not yet confirmed with a screen reader. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ src }}assets/styles.less"><code>assets/styles.less</code></a>: .left, .right and .multiCol layouts: confirm reading order with a screen reader</li></ul>{:/} |
| [1.3.3 Sensory Characteristics](https://www.w3.org/TR/WCAG21/#sensory-characteristics) | Partially Supports | About 35 passages in the slides refer to content by position or colour alone (for example "on the left" or "the red line") without another way to identify it. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): search each deck for "on the left", "on the right", and colour names</a></li></ul>{:/} |
| [1.4.1 Use of Color](https://www.w3.org/TR/WCAG21/#use-of-color) | Partially Supports | Links inside paragraphs on regular pages are distinguished from the surrounding text by colour alone (no underline), and the two colours differ by less than 3:1. Selected topic tags on the home page are indicated by colour alone. A few slides use red text alone for emphasis. Individual charts shown in the slides have not been reviewed. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}assets/style.css"><code>assets/style.css</code></a>: underline links in body text</li><li><a href="{{ src }}_layouts/index.html"><code>_layouts/index.html</code></a>: topic tags: add a non-colour selected state</li><li><a href="{{ src }}week01/lecture01p1.md"><code>week01/lecture01p1.md</code></a>: red-only emphasis</li><li><a href="{{ src }}week02/lecture02p1.md"><code>week02/lecture02p1.md</code></a>: red-only emphasis</li></ul>{:/} |
| [1.4.2 Audio Control](https://www.w3.org/TR/WCAG21/#audio-control) | Supports | No audio plays automatically. Embedded videos start only when the user plays them. | {% include a11y_status.html s="none" %} |
| [2.1.1 Keyboard](https://www.w3.org/TR/WCAG21/#keyboard) | Partially Supports | Links on regular pages and slide navigation (arrow keys, space) work from the keyboard. Exceptions: the menu button shown on narrow screens cannot be reached by keyboard and currently does not open the menu for any user, so the Syllabus, Slack, Canvas, and GitHub links are unavailable on small screens; the topic tags on the home page respond to mouse clicks only; and the interactive charts in two slide decks rely on the mouse. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_includes/header.html"><code>_includes/header.html</code></a>: menu button: make it a real button and fix its target id</li><li><a href="{{ src }}_layouts/index.html"><code>_layouts/index.html</code></a>: topic tags: make keyboard operable</li><li><a href="{{ src }}week08/lecture08p2.md"><code>week08/lecture08p2.md</code></a>: interactive charts</li></ul>{:/} |
| [2.1.2 No Keyboard Trap](https://www.w3.org/TR/WCAG21/#no-keyboard-trap) | Supports | No component is known to trap keyboard focus. Not yet confirmed by hands-on testing of the embedded video players. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ src }}week06/lecture06.md"><code>week06/lecture06.md</code></a>: tab into and out of each embedded video player</li><li><a href="{{ src }}week07/lecture07p2.md"><code>week07/lecture07p2.md</code></a>: tab into and out of each embedded video player</li><li><a href="{{ src }}week10/lecture11p2.md"><code>week10/lecture11p2.md</code></a>: tab into and out of each embedded video player</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: tab into and out of each embedded video player</li></ul>{:/} |
| [2.1.4 Character Key Shortcuts](https://www.w3.org/TR/WCAG21/#character-key-shortcuts) | Partially Supports | Regular pages have no single-key shortcuts. Lecture slides use the reveal.js single-letter shortcuts (for example N, P, F, S, O, B), and the website gives no way to turn them off or change them. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_layouts/lecture.html"><code>_layouts/lecture.html</code></a>: Reveal.initialize keyboard settings</li></ul>{:/} |
| [2.2.1 Timing Adjustable](https://www.w3.org/TR/WCAG21/#timing-adjustable) | Not Applicable | The website sets no time limits. | {% include a11y_status.html s="none" %} |
| [2.2.2 Pause, Stop, Hide](https://www.w3.org/TR/WCAG21/#pause-stop-hide) | Partially Supports | Slides contain animated GIFs that loop continuously and cannot be paused. Slide transitions themselves are turned off. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): "GIFs" column; replace with pausable video or a still image plus link</a></li></ul>{:/} |
| [2.3.1 Three Flashes or Below Threshold](https://www.w3.org/TR/WCAG21/#three-flashes-or-below-threshold) | Supports | No flashing content was identified. The animated GIFs and embedded videos have not been measured with a flash analysis tool. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): "GIFs" column; check each animation for flashing</a></li><li><a href="{{ src }}week06/lecture06.md"><code>week06/lecture06.md</code></a>: check for flashing</li><li><a href="{{ src }}week07/lecture07p2.md"><code>week07/lecture07p2.md</code></a>: check for flashing</li><li><a href="{{ src }}week10/lecture11p2.md"><code>week10/lecture11p2.md</code></a>: check for flashing</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: check for flashing</li></ul>{:/} |
| [2.4.1 Bypass Blocks](https://www.w3.org/TR/WCAG21/#bypass-blocks) | Supports | Regular pages use header, navigation, main, and footer regions and headings, which let assistive technology jump past the navigation bar. There is no visible "skip to content" link. | {% include a11y_status.html s="none" %} |
| [2.4.2 Page Titled](https://www.w3.org/TR/WCAG21/#page-titled) | Partially Supports | Regular pages and slide decks have descriptive titles. The notebook viewer page has no title. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}nbv.html"><code>nbv.html</code></a>: add a title element</li></ul>{:/} |
| [2.4.3 Focus Order](https://www.w3.org/TR/WCAG21/#focus-order) | Supports | Focus follows the order of the page source, which matches the visual order. | {% include a11y_status.html s="none" %} |
| [2.4.4 Link Purpose (In Context)](https://www.w3.org/TR/WCAG21/#link-purpose-in-context) | Partially Supports | Most links have descriptive text. Exceptions: the weekly illustration links on the home page have no text alternative, so they have no name for screen reader users; some slides and the syllabus show a bare web address as the link text. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_layouts/index.html"><code>_layouts/index.html</code></a>: image links need a text alternative</li><li><a href="{{ src }}_includes/class_info.html"><code>_includes/class_info.html</code></a>: bare web addresses used as link text</li></ul>{:/} |
| [2.5.1 Pointer Gestures](https://www.w3.org/TR/WCAG21/#pointer-gestures) | Supports | Swiping between slides on touch screens has single-tap alternatives (the on-screen arrows) and keyboard alternatives. | {% include a11y_status.html s="none" %} |
| [2.5.2 Pointer Cancellation](https://www.w3.org/TR/WCAG21/#pointer-cancellation) | Supports | Links and controls act when the pointer is released, using standard browser behaviour. | {% include a11y_status.html s="none" %} |
| [2.5.3 Label in Name](https://www.w3.org/TR/WCAG21/#label-in-name) | Supports | Controls with visible text use that text as their name. | {% include a11y_status.html s="none" %} |
| [2.5.4 Motion Actuation](https://www.w3.org/TR/WCAG21/#motion-actuation) | Not Applicable | Nothing on the website is operated by moving the device. | {% include a11y_status.html s="none" %} |
| [3.1.1 Language of Page](https://www.w3.org/TR/WCAG21/#language-of-page) | Partially Supports | Regular pages and the notebook viewer declare English as the page language. Lecture slide pages do not declare a language. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_layouts/lecture.html"><code>_layouts/lecture.html</code></a>: add lang="en" to the html tag</li></ul>{:/} |
| [3.2.1 On Focus](https://www.w3.org/TR/WCAG21/#on-focus) | Supports | Moving focus to an element does not change the page. | {% include a11y_status.html s="none" %} |
| [3.2.2 On Input](https://www.w3.org/TR/WCAG21/#on-input) | Not Applicable | The website has no forms or settings. | {% include a11y_status.html s="none" %} |
| [3.3.1 Error Identification](https://www.w3.org/TR/WCAG21/#error-identification) | Not Applicable | The website has no forms or other user input. | {% include a11y_status.html s="none" %} |
| [3.3.2 Labels or Instructions](https://www.w3.org/TR/WCAG21/#labels-or-instructions) | Not Applicable | The website has no forms or other user input. | {% include a11y_status.html s="none" %} |
| [4.1.1 Parsing](https://www.w3.org/TR/WCAG21/#parsing) | Supports | Per the [W3C's 2023 note on this criterion](https://www.w3.org/WAI/WCAG21/Understanding/parsing.html), it is treated as always satisfied for HTML content. The templates do contain a few markup errors (a stray closing tag in the slide template, incorrectly nested lists in the syllabus header) that do not affect this rating. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ src }}_layouts/lecture.html"><code>_layouts/lecture.html</code></a>: stray closing style tag</li><li><a href="{{ src }}_includes/class_info.html"><code>_includes/class_info.html</code></a>: incorrectly nested lists</li></ul>{:/} |
| [4.1.2 Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value) | Partially Supports | Standard links make up nearly all controls. Exceptions: the small-screen menu button is not focusable and never updates its expanded or collapsed state; the home page topic tags act as buttons but are not exposed as such; six of the nine embedded videos have no frame title; and the image links on the home page have no name. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_includes/header.html"><code>_includes/header.html</code></a>: menu button: focusable, update aria-expanded</li><li><a href="{{ src }}_layouts/index.html"><code>_layouts/index.html</code></a>: topic tags and image links</li><li><a href="{{ src }}week06/lecture06.md"><code>week06/lecture06.md</code></a>: add a title to each iframe</li><li><a href="{{ src }}week07/lecture07p2.md"><code>week07/lecture07p2.md</code></a>: add a title to each iframe</li><li><a href="{{ src }}week10/lecture11p2.md"><code>week10/lecture11p2.md</code></a>: add a title to each iframe</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: add a title to each iframe</li></ul>{:/} |

### Table 2: Success Criteria, Level AA

| Criteria | Conformance level | Remarks and explanations | Status |
|---|---|---|---|
| [1.2.4 Captions (Live)](https://www.w3.org/TR/WCAG21/#captions-live) | Not Applicable | The website has no live audio or video. Live class sessions are held on other platforms. | {% include a11y_status.html s="none" %} |
| [1.2.5 Audio Description (Prerecorded)](https://www.w3.org/TR/WCAG21/#audio-description-prerecorded) | Partially Supports | The embedded third-party videos are not known to have audio description. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}week06/lecture06.md"><code>week06/lecture06.md</code></a>: find or provide an audio-described version</li><li><a href="{{ src }}week07/lecture07p2.md"><code>week07/lecture07p2.md</code></a>: find or provide an audio-described version</li><li><a href="{{ src }}week10/lecture11p2.md"><code>week10/lecture11p2.md</code></a>: find or provide an audio-described version</li><li><a href="{{ src }}week11/lecture13p1.md"><code>week11/lecture13p1.md</code></a>: find or provide an audio-described version</li></ul>{:/} |
| [1.3.4 Orientation](https://www.w3.org/TR/WCAG21/#orientation) | Supports | All pages work in both portrait and landscape orientation. | {% include a11y_status.html s="none" %} |
| [1.3.5 Identify Input Purpose](https://www.w3.org/TR/WCAG21/#identify-input-purpose) | Not Applicable | The website collects no information about the user. | {% include a11y_status.html s="none" %} |
| [1.4.3 Contrast (Minimum)](https://www.w3.org/TR/WCAG21/#contrast-minimum) | Partially Supports | Body text on regular pages (about 8.9:1) and slide text (about 15.9:1) exceed the 4.5:1 minimum, and body links on regular pages just meet it (about 4.55:1). Exceptions: links in the page footer (about 4.35:1) and selected topic tags on the home page (white on green, about 2.2:1) fall below it. Text inside images and the notebook viewer's colours have not been measured. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_includes/footer.html"><code>_includes/footer.html</code></a>: footer link colour</li><li><a href="{{ src }}assets/style.css"><code>assets/style.css</code></a>: selected tag colours</li><li><a href="{{ src }}nbv.html"><code>nbv.html</code></a>: measure viewer colours</li></ul>{:/} |
| [1.4.4 Resize Text](https://www.w3.org/TR/WCAG21/#resize-text) | Partially Supports | Text on regular pages can be enlarged to 200% with browser zoom. Lecture slides cannot: the slide template disables pinch-zoom on touch devices, and reveal.js rescales each slide to fit the window, which cancels out browser zoom. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_layouts/lecture.html"><code>_layouts/lecture.html</code></a>: remove user-scalable=no; review Reveal scaling settings</li></ul>{:/} |
| [1.4.5 Images of Text](https://www.w3.org/TR/WCAG21/#images-of-text) | Partially Supports | Most code in the slides is real text. Some slides show screenshots of code, terminal output, or file contents where text could be used instead. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): replace screenshots of code with text</a></li></ul>{:/} |
| [1.4.10 Reflow](https://www.w3.org/TR/WCAG21/#reflow) | Partially Supports | Regular pages reflow to a single column on narrow screens, although the navigation menu is then unavailable (see 2.1.1) and wide syllabus tables need horizontal scrolling. Lecture slides have a fixed 1024 by 768 layout that shrinks to fit the screen instead of reflowing. The notebook viewer needs horizontal scrolling for wide code and output. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}_layouts/lecture.html"><code>_layouts/lecture.html</code></a>: fixed 1024 by 768 slide size</li><li><a href="{{ src }}_includes/header.html"><code>_includes/header.html</code></a>: small-screen menu</li><li><a href="{{ src }}syllabus.md"><code>syllabus.md</code></a>: wide tables</li><li><a href="{{ src }}nbv.html"><code>nbv.html</code></a>: wide code and output</li></ul>{:/} |
| [1.4.11 Non-text Contrast](https://www.w3.org/TR/WCAG21/#non-text-contrast) | Partially Supports | Controls and focus indicators use browser and framework defaults that meet the 3:1 minimum. The contrast of lines, marks, and labels within individual charts and diagrams shown in the slides has not been reviewed. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="#slide-decks-to-check">Slide decks to check (table below): check contrast within charts and diagrams</a></li></ul>{:/} |
| [1.4.12 Text Spacing](https://www.w3.org/TR/WCAG21/#text-spacing) | Partially Supports | Regular pages do not restrict text spacing. On lecture slides, which have a fixed size, increased spacing can push text off the slide. Not yet tested in a browser. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ src }}assets/styles.less"><code>assets/styles.less</code></a>: test slides with increased text spacing</li><li><a href="{{ src }}_layouts/lecture.html"><code>_layouts/lecture.html</code></a>: slide size settings</li></ul>{:/} |
| [1.4.13 Content on Hover or Focus](https://www.w3.org/TR/WCAG21/#content-on-hover-or-focus) | Partially Supports | Regular pages show no custom pop-up content. Tooltips on the interactive charts in two slide decks disappear when the pointer moves onto them and cannot be dismissed from the keyboard. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}week08/lecture08p2.md"><code>week08/lecture08p2.md</code></a>: chart tooltips</li></ul>{:/} |
| [2.4.5 Multiple Ways](https://www.w3.org/TR/WCAG21/#multiple-ways) | Supports | The home page lists every week's lectures and materials, each weekly page lists its own, and the navigation bar appears on all regular pages. There is no search. | {% include a11y_status.html s="none" %} |
| [2.4.6 Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels) | Supports | Headings describe the content that follows them, and nearly every slide has a heading. | {% include a11y_status.html s="none" %} |
| [2.4.7 Focus Visible](https://www.w3.org/TR/WCAG21/#focus-visible) | Supports | The website does not remove the browser's default focus indicator. Not yet confirmed by hands-on testing. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ src }}assets/style.css"><code>assets/style.css</code></a>: confirm focus outline is visible on every control</li></ul>{:/} |
| [3.1.2 Language of Parts](https://www.w3.org/TR/WCAG21/#language-of-parts) | Supports | Content is written in English. No passages in other languages were identified. | {% include a11y_status.html s="none" %} |
| [3.2.3 Consistent Navigation](https://www.w3.org/TR/WCAG21/#consistent-navigation) | Supports | The navigation bar is the same, in the same order, on every regular page. | {% include a11y_status.html s="none" %} |
| [3.2.4 Consistent Identification](https://www.w3.org/TR/WCAG21/#consistent-identification) | Supports | Lectures, notebooks, data, and libraries are labelled and marked with the same icons throughout. | {% include a11y_status.html s="none" %} |
| [3.3.3 Error Suggestion](https://www.w3.org/TR/WCAG21/#error-suggestion) | Not Applicable | The website has no forms or other user input. | {% include a11y_status.html s="none" %} |
| [3.3.4 Error Prevention (Legal, Financial, Data)](https://www.w3.org/TR/WCAG21/#error-prevention-legal-financial-data) | Not Applicable | The website handles no legal, financial, or personal data. | {% include a11y_status.html s="none" %} |
| [4.1.3 Status Messages](https://www.w3.org/TR/WCAG21/#status-messages) | Partially Supports | reveal.js announces the content of each new slide to screen readers. If a notebook fails to load, the notebook viewer shows a blank page and gives no message to any user. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ src }}nbv.html"><code>nbv.html</code></a>: show a message when a notebook fails to load</li></ul>{:/} |

### Slide decks to check

Counts for each published slide deck, taken from its Markdown source. "No alt text" and
"Placeholder alt text" are images that need a description written. "Background images"
cannot carry alternative text, so their content needs describing in the slide text.
Set the status of a deck to done once all of its columns have been dealt with.

| Slide deck | Images | No alt text | Placeholder alt text | Background images | GIFs | Videos | Status |
|---|---|---|---|---|---|---|---|
| [`week01/lecture01p1.md`]({{ src }}week01/lecture01p1.md) | 11 | 1 | 8 | 0 | 0 | 0 | {% include a11y_status.html s="todo" %} |
| [`week01/lecture01p2.md`]({{ src }}week01/lecture01p2.md) | 24 | 1 | 10 | 11 | 1 | 0 | {% include a11y_status.html s="todo" %} |
| [`week02/lecture02p1.md`]({{ src }}week02/lecture02p1.md) | 29 | 9 | 0 | 7 | 0 | 0 | {% include a11y_status.html s="todo" %} |
| [`week03/lecture03p1.md`]({{ src }}week03/lecture03p1.md) | 15 | 15 | 0 | 9 | 0 | 0 | {% include a11y_status.html s="todo" %} |
| [`week03/lecture03p2.md`]({{ src }}week03/lecture03p2.md) | 57 | 57 | 0 | 9 | 18 | 0 | {% include a11y_status.html s="todo" %} |
| [`week04/lecture04p1.md`]({{ src }}week04/lecture04p1.md) | 4 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week05/lecture05p1.md`]({{ src }}week05/lecture05p1.md) | 5 | 0 | 0 | 0 | 1 | 0 | {% include a11y_status.html s="todo" %} |
| [`week05/lecture05p2.md`]({{ src }}week05/lecture05p2.md) | 12 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week06/lecture06.md`]({{ src }}week06/lecture06.md) | 15 | 0 | 0 | 9 | 0 | 1 | {% include a11y_status.html s="todo" %} |
| [`week07/lecture07p1.md`]({{ src }}week07/lecture07p1.md) | 2 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week07/lecture07p2.md`]({{ src }}week07/lecture07p2.md) | 15 | 0 | 1 | 15 | 2 | 2 | {% include a11y_status.html s="todo" %} |
| [`week08/lecture08p1.md`]({{ src }}week08/lecture08p1.md) | 5 | 0 | 0 | 11 | 1 | 0 | {% include a11y_status.html s="todo" %} |
| [`week08/lecture08p2.md`]({{ src }}week08/lecture08p2.md) | 5 | 0 | 0 | 0 | 3 | 0 | {% include a11y_status.html s="todo" %} |
| [`week09/lecture9p1.md`]({{ src }}week09/lecture9p1.md) | 0 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week09/lecture9p2.md`]({{ src }}week09/lecture9p2.md) | 27 | 1 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="todo" %} |
| [`week10/lecture11p1.md`]({{ src }}week10/lecture11p1.md) | 1 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week10/lecture11p2.md`]({{ src }}week10/lecture11p2.md) | 19 | 0 | 0 | 0 | 3 | 2 | {% include a11y_status.html s="todo" %} |
| [`week10/lecture11p3.md`]({{ src }}week10/lecture11p3.md) | 8 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week11/lecture12p1.md`]({{ src }}week11/lecture12p1.md) | 9 | 0 | 0 | 0 | 1 | 0 | {% include a11y_status.html s="todo" %} |
| [`week11/lecture12p2.md`]({{ src }}week11/lecture12p2.md) | 2 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week11/lecture13p1.md`]({{ src }}week11/lecture13p1.md) | 30 | 0 | 0 | 0 | 3 | 4 | {% include a11y_status.html s="todo" %} |
| [`week12/lecture13p1.md`]({{ src }}week12/lecture13p1.md) | 1 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week13/lecture14p1.md`]({{ src }}week13/lecture14p1.md) | 1 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week15/lecture16p1.md`]({{ src }}week15/lecture16p1.md) | 1 | 0 | 0 | 0 | 0 | 0 | {% include a11y_status.html s="none" %} |
| [`week16/lecture16p2.md`]({{ src }}week16/lecture16p2.md) | 25 | 0 | 0 | 0 | 16 | 0 | {% include a11y_status.html s="todo" %} |
| [`week16/lecture16p3.md`]({{ src }}week16/lecture16p3.md) | 21 | 0 | 0 | 0 | 2 | 0 | {% include a11y_status.html s="todo" %} |
| **Total** | **344** | **84** | **19** | **71** | **51** | **9** | |

### Downloadable files

Jupyter notebooks, Python files, and data files are provided for students to download and
run in their own software; their accessibility there depends on that software. The repository holds one PDF (15 pages
of Jekyll tour notes in the Week 9 folder). It is not tagged for screen readers, so its
headings, reading order, and images are not exposed to assistive technology.

### Legal disclaimer

This document is provided for information purposes only and its contents are subject to
change without notice. It is offered in good faith, on the basis of the evaluation methods
described above, and is not a legally binding claim or a warranty of any kind. If you find
an error in this report or a barrier that is not listed, please contact
[{{ ii.email }}](mailto:{{ ii.email }}).
