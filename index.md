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

    <li class="mb3 mb4-ns b"><a class="pv1 no-underline" href="{{ post.url }}">{{ post.title }}</a> <time class="mt1 db normal f6 gray c-sans-serif">{{ post.date | date: "%b %d, %Y" }}</time></li>

{% endunless %}

{% endfor %}

</ul>

<hr class="pb4">

<ul class="c-linky-visited">

    <li><a href="/feed/index.xml/">RSS feed</a></li>
    <li><a href="https://mobile.twitter.com/leonpaternoster/">Twitter</a></li>
    <li><a href="https://micro.blog/leonp/">micro.blog</a></li>
    <li>leon.paternoster@zoho.com</li>

</ul>
