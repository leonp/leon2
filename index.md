---
layout: default
title: Home
display-title: 'Leon Paternoster'
is_home: true
in_nav: true
order: 1
category: work
prose-headings: true
hyphens: true
---

## Posts

<ul class="list mb0 mh0 mt4 pa0 c-linky-visited">

{% for post in site.posts limit:3 %}

    <li class="pb3"><a class="b db c-lh-title no-underline" href="{{ post.url }}">{{ post.title }}</a> <time class="mv1 f6 silver c-lh-copy">{{ post.date | date: "%b %d, %Y" }}</time></li>

{% endfor %}

</ul>

<p class="c-linky-underline c-linky-visited"><a href="/posts/">All posts &rarr;</a></p>

## Links

{% assign links = site.links | sort: "date" | reverse %}

<ul class="list mb0 mh0 mt4 pa0 c-linky-visited">

{% for link in links limit:3 %}

    <li class="pb3"><a class="b db c-lh-title no-underline" href="{{ link.url }}">{{ link.title }}</a> <time class="mv1 f6 silver c-lh-copy">{{ link.date | date: "%b %d, %Y" }}</time></li>

{% endfor %}

</ul>

<p class="c-linky-underline c-linky-visited"><a href="/links/">All links &rarr;</a></p>

## Notes

{% assign notes = site.notes | sort: "date" | reverse %}

<ul class="list mb0 mh0 mt4 pa0 c-linky-visited">

{% for note in notes limit:3 %}

    <li class="pb3"><a class="b db c-lh-title no-underline" href="{{ note.url }}">{{ note.title }}</a> <time class="mv1 f6 silver c-lh-copy">{{ note.date | date: "%b %d, %Y" }}</time></li>

{% endfor %}

</ul>

<p class="c-linky-underline c-linky-visited"><a href="/notes/">All notes &rarr;</a></p>
