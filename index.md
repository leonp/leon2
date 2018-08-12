---
layout: default
title: Home
display-title: "Leon Paternoster"
is_home: true
order: 1
---

{% assign posts = site.posts | where_exp: "post", "post.note != true" %}

<ul class="list ma0 pa0 c-linky-visited">

{% include list.html post-limit=20 %}

</ul>

<hr class="pb4">

<ul class="c-linky-visited">

    <li><a href="/feed/index.xml/">RSS feed</a></li>
    <li><a href="https://mobile.twitter.com/leonpaternoster/">Twitter</a></li>
    <li><a href="https://micro.blog/leonp/">micro.blog</a></li>
    <li>leon.paternoster@zoho.com</li>

</ul>
