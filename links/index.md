---
layout: default
title: Links
order: 5
in_nav: true
---

<ul class="ma0 pa0 list c-linky-visited c-sans-serif">

{% assign links = site.links | reverse %}

{% for link in links %}

    <li class="pt1 pb2"><a class="db b" href="{{ link.url }}">{{ link.title }}</a><time class="db f6 gray dt-published" datetime="{{ link.date | date: "%Y-%m-%d" }}">{{ link.date | date: "%b %-d, %Y" }}</time></li>

{% endfor %}

</ul>
