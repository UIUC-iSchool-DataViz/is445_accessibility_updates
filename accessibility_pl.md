---
layout: default
title: Accessibility of PrairieLearn Content
description: WCAG 2.1 conformance report for this course's PrairieLearn assessments and questions
---

{% assign co = site.data.class.course %}
{% assign ii = site.data.class.instructor %}
{% comment %} Where the PrairieLearn course content lives. Change these two lines each semester. {% endcomment %}
{% assign plq = "https://github.com/PrairieLearn/pl-is445/blob/master/questions/" %}
{% assign pla = "https://github.com/PrairieLearn/pl-is445/blob/master/courseInstances/Fa26BU/assessments/" %}

This is the report for the course's PrairieLearn content. See also the
[accessibility overview]({{ '/accessibility_home' | relative_url }}) and the
[report for the course website]({{ '/accessibility' | relative_url }}).

## Accessibility Statement

Quizzes, labs, homeworks, and the final project for {{ co.number }} ({{ co.name }}) are
delivered through [PrairieLearn](https://www.prairielearn.com/). This page documents how the
assessments and questions we have written for PrairieLearn measure up against the
[Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/) at Levels A
and AA, including the places where they fall short.

If any assessment is a barrier for you, please contact the instructor at
[{{ ii.email }}](mailto:{{ ii.email }}). You do not need to wait for a fix: we will
provide the assessment in a form that works for you.

## Conformance Report

This report follows the structure of the
[VPAT® 2.4Rev WCAG edition](https://www.itic.org/policy/accessibility/vpat).

| | |
|---|---|
| **Name of product** | {{ co.number }} {{ co.name }} assessments on PrairieLearn, {{ co.semester }}, section {{ co.section }} |
| **Location** | Course instance `Fa26BU` in the [`pl-is445`](https://github.com/PrairieLearn/pl-is445) course repository (access is limited to course staff) |
| **Report date** | November 2026 |
| **Description** | 50 assessments that together use 183 questions: quizzes, labs, homeworks, extra credit, the final project, and ungraded in-class workspaces. |
| **Contact** | {{ ii.name }}, [{{ ii.email }}](mailto:{{ ii.email }}) |
| **Standard** | [WCAG 2.1](https://www.w3.org/TR/WCAG21/) Level A and Level AA |

### Scope

The report covers the content the course staff wrote: the question text, figures, tables,
and answer inputs of every question used by an assessment in this course instance, and the
starter notebooks that open in workspaces.

It does not cover the PrairieLearn platform itself (page layout, navigation, the standard
question elements, grading messages). PrairieLearn publishes its own
[conformance report](https://www.prairielearn.com/accessibility), and where a criterion is
decided by the platform, the remarks below say so. It also does not cover the JupyterLab and
VS Code applications that run inside workspaces, beyond the notes in the
[Workspaces](#workspaces) table.

### Evaluation methods

Every assessment in `courseInstances/Fa26BU/assessments` was traced to the questions it
uses, and the source of each of those 183 questions (`question.html`, `info.json`,
`server.py`, and workspace notebooks) was reviewed. The questions break down as follows:
83 multiple choice, 25 checkbox,
7 dropdown, 6 drag-and-drop ordering,
3 matching, 45 workspace, 14 with hand-written form
controls, and a small number of text, number, and file-upload questions.

The following have **not** yet been done, and ratings may change once they are:

- opening each question in PrairieLearn as a student;
- testing with a screen reader or with the keyboard only;
- checking captions on linked recordings;
- reviewing randomly generated variants of questions beyond their templates;
- evaluating the workspace applications.

### Terms

The terms used in the "Conformance level" column are defined as follows:

- **Supports**: the content has at least one method that meets the criterion without known
  defects, or meets it with equivalent facilitation.
- **Partially Supports**: some content does not meet the criterion.
- **Does Not Support**: the majority of the content does not meet the criterion.
- **Not Applicable**: the criterion is not relevant to the content.

### Status

The "Status" column in each table tracks our progress on that criterion. Each entry lists
the questions to look at. Links go to the question's folder in the course repository, and
the link text is its path under `questions/`.

{% include a11y_legend.html %}

### Table 1: Success Criteria, Level A

| Criteria | Conformance level | Remarks and explanations | Status |
|---|---|---|---|
| [1.1.1 Non-text Content](https://www.w3.org/TR/WCAG21/#non-text-content) | Partially Supports | Question pages contain 16 figures across 8 questions; 4 of them, in 4 questions, have no alternative text. Three of those are colour figures generated when the question is opened. Workspace notebooks contain 5 instructional images across 5 questions, none with alternative text. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ plq }}LABS/lab_streamlit_setup_streamlitio/question.html"><code>LABS/lab_streamlit_setup_streamlitio</code></a>: add alt text to the figure</li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/colormaps/question.html"><code>QUIZZES/colors2_andChannels/colormaps</code></a>: add alt text to the figure</li><li><a href="{{ plq }}QUIZZES/colors1/easy_colors/question.html"><code>QUIZZES/colors1/easy_colors</code></a>: add alt text to the figure</li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/harder_colors/question.html"><code>QUIZZES/colors2_andChannels/harder_colors</code></a>: add alt text to the figure</li><li><a href="{{ plq }}FINAL_PROJECT/finalProject_Part3.1_jekyllwebpage/workspace"><code>FINAL_PROJECT/finalProject_Part3.1_jekyllwebpage</code></a>: notebook image without alt text</li><li><a href="{{ plq }}FINAL_PROJECT/finalProject_Part3.4_jekyllwebpage/workspace"><code>FINAL_PROJECT/finalProject_Part3.4_jekyllwebpage</code></a>: notebook image without alt text</li><li><a href="{{ plq }}HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/notebook/workspace"><code>HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/notebook</code></a>: notebook image without alt text</li><li><a href="{{ plq }}LABS/week2_lab_wget/workspace"><code>LABS/week2_lab_wget</code></a>: notebook image without alt text</li><li><a href="{{ plq }}LABS/week4_ipywidgets_plotting/workspace"><code>LABS/week4_ipywidgets_plotting</code></a>: notebook image without alt text</li></ul>{:/} |
| [1.2.1 Audio-only and Video-only (Prerecorded)](https://www.w3.org/TR/WCAG21/#audio-only-and-video-only-prerecorded) | Not Applicable | No audio-only or video-only media is included in the questions. | {% include a11y_status.html s="none" %} |
| [1.2.2 Captions (Prerecorded)](https://www.w3.org/TR/WCAG21/#captions-prerecorded) | Partially Supports | No video is embedded in a question. 3 questions link to recordings (course recordings on Illinois MediaSpace, and one YouTube video). Their captions have not yet been checked. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ plq }}LABS/lab_github_pages_setup2/question.html"><code>LABS/lab_github_pages_setup2</code></a>: open each linked recording and check captions</li><li><a href="{{ plq }}LABS/lab_installJekyllTemplate_dynamic/question.html"><code>LABS/lab_installJekyllTemplate_dynamic</code></a>: open each linked recording and check captions</li><li><a href="{{ plq }}QUIZZES/prep_for_bqplot_lab/flipped_class/question.html"><code>QUIZZES/prep_for_bqplot_lab/flipped_class</code></a>: open each linked recording and check captions</li></ul>{:/} |
| [1.2.3 Audio Description or Media Alternative (Prerecorded)](https://www.w3.org/TR/WCAG21/#audio-description-or-media-alternative-prerecorded) | Partially Supports | The linked recordings are not known to have audio description, and it has not been confirmed that the written instructions cover everything they show. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ plq }}LABS/lab_github_pages_setup2/question.html"><code>LABS/lab_github_pages_setup2</code></a>: check the written instructions cover everything shown in the recording</li><li><a href="{{ plq }}LABS/lab_installJekyllTemplate_dynamic/question.html"><code>LABS/lab_installJekyllTemplate_dynamic</code></a>: check the written instructions cover everything shown in the recording</li><li><a href="{{ plq }}QUIZZES/prep_for_bqplot_lab/flipped_class/question.html"><code>QUIZZES/prep_for_bqplot_lab/flipped_class</code></a>: check the written instructions cover everything shown in the recording</li></ul>{:/} |
| [1.3.1 Info and Relationships](https://www.w3.org/TR/WCAG21/#info-and-relationships) | Partially Supports | Multiple-choice, checkbox, and similar questions use PrairieLearn elements, which supply the structure. The intake survey questions correctly group their options with fieldsets, legends, and labels. Exceptions: 14 questions contain a grading rubric table with no header cells and several empty columns, and 3 questions imitate notebook cells using visual styling only. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#questions-to-check">Questions to check (table below): every row marked "table without header cells"</a></li><li><a href="{{ plq }}QUIZZES/pl_autograder_issues/deleting_grade/question.html"><code>QUIZZES/pl_autograder_issues/deleting_grade</code></a>: mock notebook cells</li><li><a href="{{ plq }}QUIZZES/pl_autograder_issues/grade_libraries/question.html"><code>QUIZZES/pl_autograder_issues/grade_libraries</code></a>: mock notebook cells</li><li><a href="{{ plq }}QUIZZES/pl_autograder_issues/renaming_vars/question.html"><code>QUIZZES/pl_autograder_issues/renaming_vars</code></a>: mock notebook cells</li></ul>{:/} |
| [1.3.2 Meaningful Sequence](https://www.w3.org/TR/WCAG21/#meaningful-sequence) | Supports | Question content is written in reading order. | {% include a11y_status.html s="none" %} |
| [1.3.3 Sensory Characteristics](https://www.w3.org/TR/WCAG21/#sensory-characteristics) | Supports | No instruction was found that relies on shape, colour, or position alone. References such as "the figure below" follow the reading order. Not yet confirmed by reading every question in PrairieLearn. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="#questions-to-check">Questions to check (table below)</a></li></ul>{:/} |
| [1.4.1 Use of Color](https://www.w3.org/TR/WCAG21/#use-of-color) | Partially Supports | 3 quiz questions ask students to identify a colour or colour map from a figure, so they cannot be answered without colour vision. Identifying colours is part of what the course teaches, but these questions currently have no alternative form. Rubric tables use alternating row colours for decoration only. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ plq }}QUIZZES/colors1/easy_colors/question.html"><code>QUIZZES/colors1/easy_colors</code></a>: decide on an alternative form of this question</li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/harder_colors/question.html"><code>QUIZZES/colors2_andChannels/harder_colors</code></a>: decide on an alternative form of this question</li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/colormaps/question.html"><code>QUIZZES/colors2_andChannels/colormaps</code></a>: decide on an alternative form of this question</li></ul>{:/} |
| [1.4.2 Audio Control](https://www.w3.org/TR/WCAG21/#audio-control) | Not Applicable | No audio plays automatically. | {% include a11y_status.html s="none" %} |
| [2.1.1 Keyboard](https://www.w3.org/TR/WCAG21/#keyboard) | Partially Supports | Multiple-choice, checkbox, dropdown, matching, and text-entry questions can be answered from the keyboard. 6 questions use drag-and-drop ordering, whose keyboard operation has not yet been confirmed. 45 questions open a workspace (JupyterLab or VS Code in the browser); these can be driven from the keyboard, but interactive charts that students build with bqplot, ipywidgets, and Altair respond mainly to the mouse. PrairieLearn itself reports this criterion as partially supported. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ plq }}HOMEWORKS/module1_courseIntro/syllabus_quiz/assignment_order/question.html"><code>HOMEWORKS/module1_courseIntro/syllabus_quiz/assignment_order</code></a>: drag-and-drop ordering: test with keyboard only</li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/perception_channels_order/question.html"><code>QUIZZES/colors2_andChannels/perception_channels_order</code></a>: drag-and-drop ordering: test with keyboard only</li><li><a href="{{ plq }}QUIZZES/grammar_of_graphics/order_gog/question.html"><code>QUIZZES/grammar_of_graphics/order_gog</code></a>: drag-and-drop ordering: test with keyboard only</li><li><a href="{{ plq }}QUIZZES/hand_wavy_web_intro/dom_intro/question.html"><code>QUIZZES/hand_wavy_web_intro/dom_intro</code></a>: drag-and-drop ordering: test with keyboard only</li><li><a href="{{ plq }}QUIZZES/vizaudience/viz_order/question.html"><code>QUIZZES/vizaudience/viz_order</code></a>: drag-and-drop ordering: test with keyboard only</li><li><a href="{{ plq }}QUIZZES/threeD_geometry/rendering_order/question.html"><code>QUIZZES/threeD_geometry/rendering_order</code></a>: drag-and-drop ordering: test with keyboard only</li><li><a href="#workspaces">Workspaces (table below)</a></li></ul>{:/} |
| [2.1.2 No Keyboard Trap](https://www.w3.org/TR/WCAG21/#no-keyboard-trap) | Supports | Code editors in the workspaces capture the Tab key for indenting; JupyterLab and VS Code each provide a documented key to leave the editor (Escape, and Ctrl+M, respectively). | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="#workspaces">Workspaces (table below): confirm by keyboard-only testing</a></li></ul>{:/} |
| [2.1.4 Character Key Shortcuts](https://www.w3.org/TR/WCAG21/#character-key-shortcuts) | Supports | Question pages add no shortcuts. JupyterLab single-key shortcuts work only while a notebook cell has focus. | {% include a11y_status.html s="none" %} |
| [2.2.1 Timing Adjustable](https://www.w3.org/TR/WCAG21/#timing-adjustable) | Supports | No assessment in this course instance has a time limit. Due dates are set per assessment and can be extended for individual students. | {% include a11y_status.html s="none" %} |
| [2.2.2 Pause, Stop, Hide](https://www.w3.org/TR/WCAG21/#pause-stop-hide) | Not Applicable | Question pages contain no moving, blinking, or auto-updating content. | {% include a11y_status.html s="none" %} |
| [2.3.1 Three Flashes or Below Threshold](https://www.w3.org/TR/WCAG21/#three-flashes-or-below-threshold) | Supports | No flashing content. | {% include a11y_status.html s="none" %} |
| [2.4.1 Bypass Blocks](https://www.w3.org/TR/WCAG21/#bypass-blocks) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [2.4.2 Page Titled](https://www.w3.org/TR/WCAG21/#page-titled) | Supports | Every assessment and question has a title. The 14 in-class notebook assessments share one title and are told apart by their number. | {% include a11y_status.html s="none" %} |
| [2.4.3 Focus Order](https://www.w3.org/TR/WCAG21/#focus-order) | Supports | Inputs appear in the source in the order they are meant to be answered. | {% include a11y_status.html s="none" %} |
| [2.4.4 Link Purpose (In Context)](https://www.w3.org/TR/WCAG21/#link-purpose-in-context) | Partially Supports | Most links have descriptive text. 5 questions contain a link whose text is only "here" or "link". | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ plq }}FINAL_PROJECT/finalProject_Part3.1_jekyllwebpage/question.html"><code>FINAL_PROJECT/finalProject_Part3.1_jekyllwebpage</code></a>: reword the link text</li><li><a href="{{ plq }}FINAL_PROJECT/finalProject_Part3.4_jekyllwebpage/question.html"><code>FINAL_PROJECT/finalProject_Part3.4_jekyllwebpage</code></a>: reword the link text</li><li><a href="{{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_misc/question.html"><code>HOMEWORKS/module1_courseIntro/survey/survey_dv_misc</code></a>: reword the link text</li><li><a href="{{ plq }}HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/urllink/question.html"><code>HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/urllink</code></a>: reword the link text</li><li><a href="{{ plq }}HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/notebook/question.html"><code>HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/notebook</code></a>: reword the link text</li></ul>{:/} |
| [2.5.1 Pointer Gestures](https://www.w3.org/TR/WCAG21/#pointer-gestures) | Supports | No question requires a multi-point or path-based gesture. Drag-and-drop ordering is covered under 2.1.1. | {% include a11y_status.html s="none" %} |
| [2.5.2 Pointer Cancellation](https://www.w3.org/TR/WCAG21/#pointer-cancellation) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [2.5.3 Label in Name](https://www.w3.org/TR/WCAG21/#label-in-name) | Supports | Controls take their names from their visible labels. | {% include a11y_status.html s="none" %} |
| [2.5.4 Motion Actuation](https://www.w3.org/TR/WCAG21/#motion-actuation) | Not Applicable | Nothing is operated by moving the device. | {% include a11y_status.html s="none" %} |
| [3.1.1 Language of Page](https://www.w3.org/TR/WCAG21/#language-of-page) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [3.2.1 On Focus](https://www.w3.org/TR/WCAG21/#on-focus) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [3.2.2 On Input](https://www.w3.org/TR/WCAG21/#on-input) | Supports | Choosing an answer does not submit it; students submit with the Save or Save and Grade buttons. | {% include a11y_status.html s="none" %} |
| [3.3.1 Error Identification](https://www.w3.org/TR/WCAG21/#error-identification) | Supports | PrairieLearn reports invalid or missing answers in text next to the input. The hand-written survey and URL inputs accept any text and have no error states. | {% include a11y_status.html s="none" %} |
| [3.3.2 Labels or Instructions](https://www.w3.org/TR/WCAG21/#labels-or-instructions) | Supports | Every text and number input has a label, and the 14 questions with hand-written form controls label them correctly. The 7 dropdown questions place the dropdown inside a sentence; how a screen reader announces them has not been confirmed. PrairieLearn itself reports this criterion as partially supported. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ plq }}QUIZZES/intro_lecture/dv_is/question.html"><code>QUIZZES/intro_lecture/dv_is</code></a>: check how the dropdown is announced</li><li><a href="{{ plq }}QUIZZES/grammar_of_graphics/bqplot_is/question.html"><code>QUIZZES/grammar_of_graphics/bqplot_is</code></a>: check how the dropdown is announced</li><li><a href="{{ plq }}QUIZZES/grammar_of_graphics/matplotlib_is/question.html"><code>QUIZZES/grammar_of_graphics/matplotlib_is</code></a>: check how the dropdown is announced</li><li><a href="{{ plq }}QUIZZES/grammar_of_graphics/vegalite_is/question.html"><code>QUIZZES/grammar_of_graphics/vegalite_is</code></a>: check how the dropdown is announced</li><li><a href="{{ plq }}QUIZZES/vega_lite/is_it_decl/question.html"><code>QUIZZES/vega_lite/is_it_decl</code></a>: check how the dropdown is announced</li><li><a href="{{ plq }}QUIZZES/vizaudience/viz_with_labels/question.html"><code>QUIZZES/vizaudience/viz_with_labels</code></a>: check how the dropdown is announced</li><li><a href="{{ plq }}QUIZZES/vizaudience/viz_dashboard/question.html"><code>QUIZZES/vizaudience/viz_dashboard</code></a>: check how the dropdown is announced</li></ul>{:/} |
| [4.1.1 Parsing](https://www.w3.org/TR/WCAG21/#parsing) | Supports | Per the <a href="https://www.w3.org/WAI/WCAG21/Understanding/parsing.html">W3C's 2023 note on this criterion</a>, it is treated as always satisfied for HTML content. The rubric tables and one colour question use obsolete markup (bgcolor, font) that should be replaced when they are next edited. | {% include a11y_status.html s="none" %} |
| [4.1.2 Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value) | Supports | Questions use PrairieLearn elements and standard HTML form controls, which expose their names, roles, and values. Not yet confirmed with a screen reader. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_familiarity/question.html"><code>HOMEWORKS/module1_courseIntro/survey/survey_dv_familiarity</code></a>: intake survey: test with a screen reader</li><li><a href="#questions-to-check">Questions to check (table below)</a></li></ul>{:/} |

### Table 2: Success Criteria, Level AA

| Criteria | Conformance level | Remarks and explanations | Status |
|---|---|---|---|
| [1.2.4 Captions (Live)](https://www.w3.org/TR/WCAG21/#captions-live) | Not Applicable | No live media. | {% include a11y_status.html s="none" %} |
| [1.2.5 Audio Description (Prerecorded)](https://www.w3.org/TR/WCAG21/#audio-description-prerecorded) | Partially Supports | The linked recordings are not known to have audio description. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ plq }}LABS/lab_github_pages_setup2/question.html"><code>LABS/lab_github_pages_setup2</code></a></li><li><a href="{{ plq }}LABS/lab_installJekyllTemplate_dynamic/question.html"><code>LABS/lab_installJekyllTemplate_dynamic</code></a></li><li><a href="{{ plq }}QUIZZES/prep_for_bqplot_lab/flipped_class/question.html"><code>QUIZZES/prep_for_bqplot_lab/flipped_class</code></a></li></ul>{:/} |
| [1.3.4 Orientation](https://www.w3.org/TR/WCAG21/#orientation) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [1.3.5 Identify Input Purpose](https://www.w3.org/TR/WCAG21/#identify-input-purpose) | Not Applicable | No question collects the kinds of personal information this criterion lists. | {% include a11y_status.html s="none" %} |
| [1.4.3 Contrast (Minimum)](https://www.w3.org/TR/WCAG21/#contrast-minimum) | Partially Supports | Question text uses PrairieLearn's default colours. Exceptions: one colour question shows each answer choice in its own colour on a black background, and some of those combinations fall below 4.5:1; rubric tables use 12-pixel dark text on a mid-grey background (about 4.1:1). | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="{{ plq }}QUIZZES/colors2_andChannels/harder_colors/question.html"><code>QUIZZES/colors2_andChannels/harder_colors</code></a>: coloured answer text on black</li><li><a href="#questions-to-check">Questions to check (table below): every row marked "table without header cells"</a></li></ul>{:/} |
| [1.4.4 Resize Text](https://www.w3.org/TR/WCAG21/#resize-text) | Supports | Question text is set by PrairieLearn and scales with browser zoom. Rubric tables and mock notebook cells set fixed 12 to 13 pixel text, which still scales with zoom. | {% include a11y_status.html s="none" %} |
| [1.4.5 Images of Text](https://www.w3.org/TR/WCAG21/#images-of-text) | Supports | Figures are screenshots of software, where the appearance is the point. Code is given as text. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ plq }}HOMEWORKS/module1_courseIntro/logon_slack/question.html"><code>HOMEWORKS/module1_courseIntro/logon_slack</code></a>: confirm each screenshot needs to be an image</li><li><a href="{{ plq }}HOMEWORKS/module1_courseIntro/hw1_changeWorkbook/question.html"><code>HOMEWORKS/module1_courseIntro/hw1_changeWorkbook</code></a>: confirm each screenshot needs to be an image</li><li><a href="{{ plq }}LABS/lab_installJekyllTemplate_dynamic/question.html"><code>LABS/lab_installJekyllTemplate_dynamic</code></a>: confirm each screenshot needs to be an image</li><li><a href="{{ plq }}LABS/lab_streamlit_setup_streamlitio/question.html"><code>LABS/lab_streamlit_setup_streamlitio</code></a>: confirm each screenshot needs to be an image</li><li><a href="{{ plq }}QUIZZES/course_policies/pl_question_mark_meaning/question.html"><code>QUIZZES/course_policies/pl_question_mark_meaning</code></a>: confirm each screenshot needs to be an image</li></ul>{:/} |
| [1.4.10 Reflow](https://www.w3.org/TR/WCAG21/#reflow) | Partially Supports | Standard questions reflow with the PrairieLearn page. Rubric tables are eight columns wide and need horizontal scrolling on narrow screens. Workspaces (JupyterLab, VS Code) are full applications that need a wide window. | {% include a11y_status.html s="todo" %}{::nomarkdown}<ul><li><a href="#questions-to-check">Questions to check (table below): every row marked "table without header cells"</a></li></ul>{:/} |
| [1.4.11 Non-text Contrast](https://www.w3.org/TR/WCAG21/#non-text-contrast) | Supports | Controls are PrairieLearn's. The generated colour figures have not been measured. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="{{ plq }}QUIZZES/colors1/easy_colors/question.html"><code>QUIZZES/colors1/easy_colors</code></a></li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/harder_colors/question.html"><code>QUIZZES/colors2_andChannels/harder_colors</code></a></li><li><a href="{{ plq }}QUIZZES/colors2_andChannels/colormaps/question.html"><code>QUIZZES/colors2_andChannels/colormaps</code></a></li></ul>{:/} |
| [1.4.12 Text Spacing](https://www.w3.org/TR/WCAG21/#text-spacing) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [1.4.13 Content on Hover or Focus](https://www.w3.org/TR/WCAG21/#content-on-hover-or-focus) | Partially Supports | Question content adds no pop-up content. PrairieLearn itself reports this criterion as partially supported because of its own tooltips. | {% include a11y_status.html s="none" %} |
| [2.4.5 Multiple Ways](https://www.w3.org/TR/WCAG21/#multiple-ways) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [2.4.6 Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels) | Supports | Longer questions (labs, homeworks, final project) are divided with descriptive headings; short quiz questions need none. | {% include a11y_status.html s="none" %} |
| [2.4.7 Focus Visible](https://www.w3.org/TR/WCAG21/#focus-visible) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [3.1.2 Language of Parts](https://www.w3.org/TR/WCAG21/#language-of-parts) | Supports | Question content is in English. | {% include a11y_status.html s="none" %} |
| [3.2.3 Consistent Navigation](https://www.w3.org/TR/WCAG21/#consistent-navigation) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [3.2.4 Consistent Identification](https://www.w3.org/TR/WCAG21/#consistent-identification) | Supports | Assessments are named consistently by set and number (Quiz, Lab, Homework). | {% include a11y_status.html s="none" %} |
| [3.3.3 Error Suggestion](https://www.w3.org/TR/WCAG21/#error-suggestion) | Supports | Set by the PrairieLearn platform; see its report. | {% include a11y_status.html s="none" %} |
| [3.3.4 Error Prevention (Legal, Financial, Data)](https://www.w3.org/TR/WCAG21/#error-prevention-legal-financial-data) | Supports | Answers can be saved and changed before grading. Homework-type assessments allow further attempts; quizzes ask for confirmation before they are finished. | {% include a11y_status.html s="check" %}{::nomarkdown}<ul><li><a href="#assessments-reviewed">Assessments reviewed (table below): confirm the ten Exam-type assessments</a></li></ul>{:/} |
| [4.1.3 Status Messages](https://www.w3.org/TR/WCAG21/#status-messages) | Supports | Grading results and workspace status are announced by PrairieLearn. | {% include a11y_status.html s="none" %} |

### Questions to check

The 45 questions where the review found something to fix or confirm. The other
138 questions are standard multiple-choice, checkbox, matching, or workspace
questions with nothing flagged.

| Question | Used in | What to check | Status |
|---|---|---|---|
| [`HOMEWORKS/extra_credit/sciviz`]({{ plq }}HOMEWORKS/extra_credit/sciviz/question.html) | Extra Credit 1 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/extra_credit/word_text_data`]({{ plq }}HOMEWORKS/extra_credit/word_text_data/question.html) | Extra Credit 2 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`FINAL_PROJECT/finalProject_Part1`]({{ plq }}FINAL_PROJECT/finalProject_Part1/question.html) | Final Project 1 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`FINAL_PROJECT/finalProject_Part2_workspaceSP26`]({{ plq }}FINAL_PROJECT/finalProject_Part2_workspaceSP26/question.html) | Final Project 2 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`FINAL_PROJECT/finalProject_Part3.1_streamlit_streamlitio`]({{ plq }}FINAL_PROJECT/finalProject_Part3.1_streamlit_streamlitio/question.html) | Final Project 3.1 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`FINAL_PROJECT/finalProject_Part3.1_jekyllwebpage`]({{ plq }}FINAL_PROJECT/finalProject_Part3.1_jekyllwebpage/question.html) | Final Project 3.1 | notebook image without alt text; table without header cells; link text "here" or "link" | {% include a11y_status.html s="todo" %} |
| [`FINAL_PROJECT/finalProject_Part3.4_streamlit_streamlitio`]({{ plq }}FINAL_PROJECT/finalProject_Part3.4_streamlit_streamlitio/question.html) | Final Project 3.4 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`FINAL_PROJECT/finalProject_Part3.4_jekyllwebpage`]({{ plq }}FINAL_PROJECT/finalProject_Part3.4_jekyllwebpage/question.html) | Final Project 3.4 | notebook image without alt text; table without header cells; link text "here" or "link" | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module1_courseIntro/syllabus_quiz/assignment_order`]({{ plq }}HOMEWORKS/module1_courseIntro/syllabus_quiz/assignment_order/question.html) | Homework 1 | drag-and-drop ordering: check keyboard use | {% include a11y_status.html s="check" %} |
| [`HOMEWORKS/module1_courseIntro/survey/survey_dv_familiarity`]({{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_familiarity/question.html) | Homework 1 | hand-written form controls: test with a screen reader | {% include a11y_status.html s="check" %} |
| [`HOMEWORKS/module1_courseIntro/survey/survey_dv_computer`]({{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_computer/question.html) | Homework 1 | hand-written form controls: test with a screen reader | {% include a11y_status.html s="check" %} |
| [`HOMEWORKS/module1_courseIntro/survey/survey_dv_programming`]({{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_programming/question.html) | Homework 1 | hand-written form controls: test with a screen reader | {% include a11y_status.html s="check" %} |
| [`HOMEWORKS/module1_courseIntro/survey/survey_dv_misc`]({{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_misc/question.html) | Homework 1 | link text "here" or "link"; hand-written form controls: test with a screen reader | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module1_courseIntro/survey/survey_dv_classgoals`]({{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_classgoals/question.html) | Homework 1 | hand-written form controls: test with a screen reader | {% include a11y_status.html s="check" %} |
| [`HOMEWORKS/module1_courseIntro/survey/survey_dv_anythingelse`]({{ plq }}HOMEWORKS/module1_courseIntro/survey/survey_dv_anythingelse/question.html) | Homework 1 | hand-written form controls: test with a screen reader | {% include a11y_status.html s="check" %} |
| [`HOMEWORKS/module3_colorsAndImages/hw2_images_and_colors`]({{ plq }}HOMEWORKS/module3_colorsAndImages/hw2_images_and_colors/question.html) | Homework 2 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module4_ipywidgets/hw3_widgets`]({{ plq }}HOMEWORKS/module4_ipywidgets/hw3_widgets/question.html) | Homework 3 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module7_maps/hw8_maps`]({{ plq }}HOMEWORKS/module7_maps/hw8_maps/question.html) | Homework 4 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/urllink`]({{ plq }}HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/urllink/question.html) | Homework 5 | table without header cells; link text "here" or "link" | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/notebook`]({{ plq }}HOMEWORKS/module9_altairJekyllIntro/hw6_jekyllwebpage/notebook/question.html) | Homework 5 | notebook image without alt text; table without header cells; link text "here" or "link" | {% include a11y_status.html s="todo" %} |
| [`HOMEWORKS/module10_streamlit/hw5_streamlit/submit_url_streamlitio`]({{ plq }}HOMEWORKS/module10_streamlit/hw5_streamlit/submit_url_streamlitio/question.html) | Homework 6 | table without header cells | {% include a11y_status.html s="todo" %} |
| [`LABS/week2_lab_wget`]({{ plq }}LABS/week2_lab_wget/question.html) | Lab 2 | notebook image without alt text | {% include a11y_status.html s="todo" %} |
| [`LABS/week4_ipywidgets_plotting`]({{ plq }}LABS/week4_ipywidgets_plotting/question.html) | Lab 3 | notebook image without alt text | {% include a11y_status.html s="todo" %} |
| [`LABS/lab_github_pages_setup2`]({{ plq }}LABS/lab_github_pages_setup2/question.html) | Lab 4 | links to a recording: check captions | {% include a11y_status.html s="check" %} |
| [`LABS/lab_installJekyllTemplate_dynamic`]({{ plq }}LABS/lab_installJekyllTemplate_dynamic/question.html) | Lab 6 | links to a recording: check captions | {% include a11y_status.html s="check" %} |
| [`LABS/lab_streamlit_setup_streamlitio`]({{ plq }}LABS/lab_streamlit_setup_streamlitio/question.html) | Lab 8 | figure without alt text | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/intro_lecture/dv_is`]({{ plq }}QUIZZES/intro_lecture/dv_is/question.html) | Quiz 1 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/pl_autograder_issues/deleting_grade`]({{ plq }}QUIZZES/pl_autograder_issues/deleting_grade/question.html) | Quiz 1 | mock notebook cells built from styled blocks | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/pl_autograder_issues/grade_libraries`]({{ plq }}QUIZZES/pl_autograder_issues/grade_libraries/question.html) | Quiz 1 | mock notebook cells built from styled blocks | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/pl_autograder_issues/renaming_vars`]({{ plq }}QUIZZES/pl_autograder_issues/renaming_vars/question.html) | Quiz 1 | mock notebook cells built from styled blocks | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/colors2_andChannels/colormaps`]({{ plq }}QUIZZES/colors2_andChannels/colormaps/question.html) | Quiz 2 | figure without alt text; depends on colour perception | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/colors2_andChannels/perception_channels_order`]({{ plq }}QUIZZES/colors2_andChannels/perception_channels_order/question.html) | Quiz 2 | drag-and-drop ordering: check keyboard use | {% include a11y_status.html s="check" %} |
| [`QUIZZES/colors1/easy_colors`]({{ plq }}QUIZZES/colors1/easy_colors/question.html) | Quiz 2 | figure without alt text; depends on colour perception | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/colors2_andChannels/harder_colors`]({{ plq }}QUIZZES/colors2_andChannels/harder_colors/question.html) | Quiz 2 | figure without alt text; depends on colour perception | {% include a11y_status.html s="todo" %} |
| [`QUIZZES/grammar_of_graphics/bqplot_is`]({{ plq }}QUIZZES/grammar_of_graphics/bqplot_is/question.html) | Quiz 3 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/grammar_of_graphics/matplotlib_is`]({{ plq }}QUIZZES/grammar_of_graphics/matplotlib_is/question.html) | Quiz 3 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/grammar_of_graphics/order_gog`]({{ plq }}QUIZZES/grammar_of_graphics/order_gog/question.html) | Quiz 3 | drag-and-drop ordering: check keyboard use | {% include a11y_status.html s="check" %} |
| [`QUIZZES/grammar_of_graphics/vegalite_is`]({{ plq }}QUIZZES/grammar_of_graphics/vegalite_is/question.html) | Quiz 3 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/prep_for_bqplot_lab/flipped_class`]({{ plq }}QUIZZES/prep_for_bqplot_lab/flipped_class/question.html) | Quiz 3 | links to a recording: check captions | {% include a11y_status.html s="check" %} |
| [`QUIZZES/vega_lite/is_it_decl`]({{ plq }}QUIZZES/vega_lite/is_it_decl/question.html) | Quiz 5 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/hand_wavy_web_intro/dom_intro`]({{ plq }}QUIZZES/hand_wavy_web_intro/dom_intro/question.html) | Quiz 5 | drag-and-drop ordering: check keyboard use | {% include a11y_status.html s="check" %} |
| [`QUIZZES/vizaudience/viz_order`]({{ plq }}QUIZZES/vizaudience/viz_order/question.html) | Quiz 7 | drag-and-drop ordering: check keyboard use | {% include a11y_status.html s="check" %} |
| [`QUIZZES/vizaudience/viz_with_labels`]({{ plq }}QUIZZES/vizaudience/viz_with_labels/question.html) | Quiz 7 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/vizaudience/viz_dashboard`]({{ plq }}QUIZZES/vizaudience/viz_dashboard/question.html) | Quiz 7 | dropdown inside a sentence: check how it is announced | {% include a11y_status.html s="check" %} |
| [`QUIZZES/threeD_geometry/rendering_order`]({{ plq }}QUIZZES/threeD_geometry/rendering_order/question.html) | Quiz 8 | drag-and-drop ordering: check keyboard use | {% include a11y_status.html s="check" %} |

### Workspaces

45 questions open a workspace built from one of these Docker images. The
applications inside them have not been evaluated.

| Workspace image | Application | Questions | Status |
|---|---|---|---|
| `jnaiman/workspace-is445-sp25` | JupyterLab | 16 | {% include a11y_status.html s="check" %} |
| `jnaiman/workspace-is445-fa26` | JupyterLab | 15 | {% include a11y_status.html s="check" %} |
| `jnaiman/workspace-is445-vscode` | VS Code | 8 | {% include a11y_status.html s="check" %} |
| `jnaiman/workspace-is445` | JupyterLab | 3 | {% include a11y_status.html s="check" %} |
| `jnaiman/workspace-is445-sp26` | JupyterLab | 2 | {% include a11y_status.html s="check" %} |
| `jnaiman/workspace-is445-nodownload` | JupyterLab | 1 | {% include a11y_status.html s="check" %} |

### Assessments reviewed

All 50 assessments in the course instance, with the number of distinct questions each
uses and how many of those appear in the table above.

| Assessment | Title | Type | Questions | Questions flagged |
|---|---|---|---|---|
| [Extra Credit 1]({{ pla }}extra_credit_sciviz/infoAssessment.json) | Extra Credit: SciViz | Homework | 1 | 1 |
| [Extra Credit 2]({{ pla }}extra_credit_word_text_viz/infoAssessment.json) | Extra Credit: Word/Text Viz | Homework | 1 | 1 |
| [Final Project 1]({{ pla }}finalProject_Part1/infoAssessment.json) | Final Project, Part 1 | Homework | 1 | 1 |
| [Final Project 2]({{ pla }}finalProject_Part2/infoAssessment.json) | Final, Part 2 | Homework | 1 | 1 |
| [Final Project 3.1]({{ pla }}finalProject_Part3.1/infoAssessment.json) | Final, Part 3.1 | Homework | 2 | 2 |
| [Final Project 3.4]({{ pla }}finalProject_Part3.4/infoAssessment.json) | Final, Part 3.4 | Homework | 2 | 2 |
| [Homework 1]({{ pla }}homework1/infoAssessment.json) | Introduction to PraireLearn, Syllabus Quiz, Intake Survey, and Logging onto Slack | Homework | 30 | 7 |
| [Homework 2]({{ pla }}homework2/infoAssessment.json) | Working with Images and Colors | Homework | 1 | 1 |
| [Homework 3]({{ pla }}homework3/infoAssessment.json) | ipywidgets in Python | Homework | 1 | 1 |
| [Homework 4]({{ pla }}homework4/infoAssessment.json) | Maps and ipywidgets | Homework | 1 | 1 |
| [Homework 5]({{ pla }}homework5_jekyll/infoAssessment.json) | Jekyll Webpage | Homework | 2 | 2 |
| [Homework 6]({{ pla }}homework6_streamlit/infoAssessment.json) | Streamlit | Homework | 1 | 1 |
| [InClass 1]({{ pla }}ungraded_inclass_week1/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 2]({{ pla }}ungraded_inclass_week2/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 3]({{ pla }}ungraded_inclass_week3/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 4]({{ pla }}ungraded_inclass_week4/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 5]({{ pla }}ungraded_inclass_week5/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 6]({{ pla }}ungraded_inclass_week6/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 7]({{ pla }}ungraded_inclass_week7/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 8]({{ pla }}ungraded_inclass_week8/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 9]({{ pla }}ungraded_inclass_week9/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 10]({{ pla }}ungraded_inclass_week10/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 11]({{ pla }}ungraded_inclass_week11/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 12]({{ pla }}ungraded_inclass_week12/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 13]({{ pla }}ungraded_inclass_week13/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [InClass 14]({{ pla }}ungraded_inclass_week14/infoAssessment.json) | UNGRADED In-class notebook | Homework | 1 | 0 |
| [Lab 1]({{ pla }}lab1_pandasPractice/infoAssessment.json) | Pandas Practice | Homework | 2 | 0 |
| [Lab 2]({{ pla }}lab2_wget/infoAssessment.json) | Practice with wget and Images | Homework | 1 | 1 |
| [Lab 3]({{ pla }}lab3_ipywidgets/infoAssessment.json) | ipywidgets Practice | Homework | 3 | 1 |
| [Lab 4]({{ pla }}lab4_github_pages_setup/infoAssessment.json) | Github Pages Setup | Homework | 1 | 1 |
| [Lab 5]({{ pla }}lab5_dashboarding/infoAssessment.json) | Dashboarding Practice with bqplot | Homework | 3 | 0 |
| [Lab 6]({{ pla }}lab6_installJekyll/infoAssessment.json) | Jekyll Template Upload to GitHub page | Homework | 1 | 1 |
| [Lab 7]({{ pla }}lab7_altair/infoAssessment.json) | Altair Practice | Homework | 2 | 0 |
| [Lab 8]({{ pla }}lab8_installStreamlit/infoAssessment.json) | Streamlit Template on Streamlit.io | Homework | 1 | 1 |
| [Quiz 1]({{ pla }}quiz1_intro_dataOps_beginningColors/infoAssessment.json) | Introduction, Data Operations; PrairieLearn Labs | Exam | 13 | 4 |
| [Quiz 2]({{ pla }}quiz2_colors_and_channels/infoAssessment.json) | Colors and Perception Channels; Reminder about Homework Extension Policies | Exam | 12 | 4 |
| [Quiz 3]({{ pla }}quiz3_ipywidgets_bqplot_GoG_flippedClass/infoAssessment.json) | ipywidgets, bqplot, Grammar of Graphics | Exam | 10 | 5 |
| [Quiz 4]({{ pla }}quiz4_dashboards_and_maps/infoAssessment.json) | Dashboards and Maps, Choosing Viz Engines | Exam | 9 | 0 |
| [Quiz 5]({{ pla }}quiz5_vegaintro_handwavyWebIntro_choosingviz/infoAssessment.json) | Intro to vega-lite, Hand-wavy intro to the web & Choosing your Viz | Exam | 11 | 2 |
| [Quiz 6]({{ pla }}quiz6_jekyll_finalProject/infoAssessment.json) | Intro to Jekyll & Final Project | Exam | 8 | 0 |
| [Quiz 7]({{ pla }}quiz7_vizAudience/infoAssessment.json) | Viz Audience | Exam | 9 | 3 |
| [Quiz 8]({{ pla }}quiz8_photorealism_and_graphics_and_publishing/infoAssessment.json) | Introduction to Graphics and Photorealism, Publishing & Final Project Part 3 | Exam | 18 | 1 |
| [Quiz 9]({{ pla }}quiz9_sciviz/infoAssessment.json) | Scientific Visualization, bit more about Final Project | Exam | 8 | 0 |
| [Quiz 10]({{ pla }}quiz10_networks_and_wordclouds/infoAssessment.json) | Network Viz and Wordclouds | Exam | 10 | 0 |
| [VSCode 9]({{ pla }}ungraded_vscode_inclass_week9/infoAssessment.json) | UNGRADED In-class VSCode Workspace | Homework | 1 | 0 |
| [VSCode 10]({{ pla }}ungraded_vscode_inclass_week10/infoAssessment.json) | UNGRADED In-class VSCode Workspace | Homework | 1 | 0 |
| [VSCode 11]({{ pla }}ungraded_vscode_inclass_week11/infoAssessment.json) | UNGRADED In-class VSCode Workspace | Homework | 1 | 0 |
| [VSCode 12]({{ pla }}ungraded_vscode_inclass_week12/infoAssessment.json) | UNGRADED In-class VSCode Workspace | Homework | 1 | 0 |
| [VSCode 13]({{ pla }}ungraded_vscode_inclass_week13/infoAssessment.json) | UNGRADED In-class VSCode Workspace | Homework | 1 | 0 |
| [VSCode 14]({{ pla }}ungraded_vscode_inclass_week14/infoAssessment.json) | UNGRADED In-class VSCode Workspace | Homework | 1 | 0 |

### Legal disclaimer

This document is provided for information purposes only and its contents are subject to
change without notice. It is offered in good faith, on the basis of the evaluation methods
described above, and is not a legally binding claim or a warranty of any kind. If you find
an error in this report or a barrier that is not listed, please contact
[{{ ii.email }}](mailto:{{ ii.email }}).
