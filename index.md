---
layout: default
title: Home
display-title: "Leon Paternoster"
is_home: true
order: 1
---

{% assign posts = site.posts %}

<ul class="list ma0 pa0 c-linky-visited">

{% for post in posts limit: 20 %}

{% unless post.note %}

    <li class="mb3 mb4-ns"><a class="pv1 no-underline" href="{{ post.url }}">{{ post.title }}</a> <time class="mt1 db normal f6 gray c-sans-serif">{{ post.date | date: "%b %d, %Y" }}</time></li>

{% endunless %}

{% endfor %}

</ul>

<hr class="pb4">

- [RSS feed](/feed/index.xml/)
- [Twitter](https://mobile.twitter.com/leonpaternoster/)
- [micro.blog](https://micro.blog/leonp/)
- leon.paternoster@zoho.com
