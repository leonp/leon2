---
layout: default
title: Notes
order: 4
in_nav: true
---

<ul class="ma0 pa0 list c-linky-visited c-sans-serif">

{% assign notes = site.notes | reverse %}

{% for note in notes %}

    <li class="pt1 pb2">{{ note.content | strip_html | truncate: 75 }} <a class="db" href="{{ note.url }}"><time class="f6 dt-published" datetime="{{ note.date | date: "%Y-%m-%d" }}">{{ note.date | date: "%b %-d, %Y" }}</time></a></li>

{% endfor %}

</ul>
