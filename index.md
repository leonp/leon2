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

## Links

<ul class="list mb0 mh0 mt4 pa0 c-linky-visited">

{% for link in site.links limit:3 %}

    <li class="pb3"><a class="b db c-lh-title no-underline" href="{{ link.url }}">{{ link.title }}</a> <time class="mv1 f6 silver c-lh-copy">{{ link.date | date: "%b %d, %Y" }}</time></li>

{% endfor %}

</ul>

## Notes

<ul class="list mb0 mh0 mt4 pa0 c-linky-visited">

{% for note in site.notes limit:3 %}

    <li class="pb3"><a class="b db c-lh-title no-underline" href="{{ note.url }}">{{ note.title }}</a> <time class="mv1 f6 silver c-lh-copy">{{ note.date | date: "%b %d, %Y" }}</time></li>

{% endfor %}

</ul>
