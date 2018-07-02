---
layout: default
title: Leon Paternoster
is_home: true
---

Personal site of Leon Paternoster. Posts on web, libraries, politics, books, music. Desde 2008.

<h2 class="f4 mt4 mb2 lh-title">Popular articles</h2>

Probably the posts you're interested in:

<ul class="list ma0 pa0">

{% assign posts = site.posts | where: 'featured', 'true' %}

{% for post in posts limit:10 %}

    <li class="mb3"><a class="pv1" href="{{ post.url }}">{{ post.title }}</a> <time class="db f6 gray">{{ post.date | date: "%b %d, %Y" }}</time></li>

{% endfor %}

</ul>
