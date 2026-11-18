---
layout: default
title: Accessibility
description: Overview of accessibility status for the course website and PrairieLearn content
---

{% assign co = site.data.class.course %}
{% assign ii = site.data.class.instructor %}

We want every student in {{ co.number }} ({{ co.name }}) to be able to use the course
materials. We measure the course against the
[Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/), Levels A
and AA, and keep two reports:

- [Course website report]({{ '/accessibility' | relative_url }}): this website, including
  the syllabus, lecture slides, and notebooks.
- [PrairieLearn content report]({{ '/accessibility_pl' | relative_url }}): the quizzes,
  labs, homeworks, and final project delivered through PrairieLearn.

If anything in the course is a barrier for you, please contact the instructor at
[{{ ii.email }}](mailto:{{ ii.email }}). You do not need to wait for a fix to be published.

## Where things stand

The numbers below are counted from the two reports each time the website is built, so they
update whenever a status in either report is changed.

{%- comment -%}
  Each report marks a status with {% raw %}{% include a11y_status.html s="..." %}{% endraw %}.  Depending on build
  order, another page's content reaches us either before that include is expanded
  (it contains s="todo") or after (it contains status-todo), so both forms are counted.
{%- endcomment -%}
{% assign reports = "accessibility.md,accessibility_pl.md" | split: "," %}
{% assign names = "Course website,PrairieLearn content" | split: "," %}
{% assign links = "/accessibility,/accessibility_pl" | split: "," %}
{% assign keys = "todo,progress,check,done,none" | split: "," %}
{% assign levels = "Supports,Partially Supports,Does Not Support,Not Applicable" | split: "," %}

{% for report in reports %}
{% assign p = site.pages | where: "name", report | first %}
{% assign c = p.content %}
{% assign counts = "" | split: "," %}
{% for k in keys %}
  {% assign raw = 's="' | append: k | append: '"' %}
  {% assign cls = "status-" | append: k %}
  {% assign n1 = c | split: raw | size | minus: 1 %}
  {% assign n2 = c | split: cls | size | minus: 1 %}
  {% assign n = n1 | plus: n2 %}
  {% assign counts = counts | push: n %}
{% endfor %}
{% assign open_items = counts[0] | plus: counts[1] | plus: counts[2] %}
{% assign tracked = open_items | plus: counts[3] %}
{% if tracked > 0 %}{% assign pct = counts[3] | times: 100 | divided_by: tracked %}{% else %}{% assign pct = 100 %}{% endif %}

<h3><a href="{{ links[forloop.index0] | relative_url }}">{{ names[forloop.index0] }}</a></h3>

<p><strong>{{ counts[3] }} of {{ tracked }}</strong> tracked items done ({{ pct }}%).</p>
<progress class="progress is-success" value="{{ counts[3] }}" max="{{ tracked }}" aria-label="{{ names[forloop.index0] }}: {{ counts[3] }} of {{ tracked }} tracked items done">{{ pct }}%</progress>

<table>
  <thead><tr><th scope="col">Status</th><th scope="col">Items</th></tr></thead>
  <tbody>
    <tr><td><strong class="tag is-danger is-light">To do</strong></td><td>{{ counts[0] }}</td></tr>
    <tr><td><strong class="tag is-link is-light">In progress</strong></td><td>{{ counts[1] }}</td></tr>
    <tr><td><strong class="tag is-info is-light">Needs check</strong></td><td>{{ counts[2] }}</td></tr>
    <tr><td><strong class="tag is-success is-light">Done</strong></td><td>{{ counts[3] }}</td></tr>
    <tr><td><strong class="tag">No action</strong></td><td>{{ counts[4] }}</td></tr>
  </tbody>
</table>

<table>
  <thead><tr><th scope="col">WCAG 2.1 conformance level (50 criteria)</th><th scope="col">Criteria</th></tr></thead>
  <tbody>
  {% for lv in levels %}
    {% assign m1 = "| " | append: lv | append: " |" %}
    {% assign m2 = "<td>" | append: lv | append: "</td>" %}
    {% assign l1 = c | split: m1 | size | minus: 1 %}
    {% assign l2 = c | split: m2 | size | minus: 1 %}
    <tr><td>{{ lv }}</td><td>{{ l1 | plus: l2 }}</td></tr>
  {% endfor %}
  </tbody>
</table>
{% endfor %}

## What the statuses mean

"Tracked items" are the rows of the tables in each report: one per WCAG criterion, plus one
per slide deck or question that needs attention.

{% include a11y_legend.html %}
