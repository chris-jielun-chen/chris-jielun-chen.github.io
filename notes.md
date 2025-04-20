---
layout: noheader
title: Notes
permalink: /notes/
---

<p style="font-size: 1.1em; line-height: 1.6; margin-bottom: 1.5em;">
These are informal research notes and observations — small results, tricks, or curiosities I came across while thinking about problems. They're not polished, but may be useful.
</p>

<ul>
  {% assign sorted_notes = site.notes | sort: "date" | reverse %}
  {% for note in sorted_notes %}
    <li style="margin-bottom: 1em;">
      <a href="{{ note.url }}" style="font-weight: bold; font-size: 1.1em;">{{ note.title }}</a>
      – {{ note.date | date: "%Y-%m-%d" }}
    </li>
  {% endfor %}
</ul>
