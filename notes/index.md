---
layout: default
title: Notes
---

<ul class="ma0 pa0 list c-linky-visited">

{% for note in site.notes %}

    <li class="pt1 pb2 f6">{{ note.content | strip_html | truncate: 75 }} <a class="db" href="{{ note.url }}"><time class="dt-published" datetime="{{ note.date | date: "%Y-%m-%d" }}">{{ note.date | date: "%b %-d, %Y" }}</time></a></li>

{% endfor %}

</ul>
