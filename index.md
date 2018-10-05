---
layout: default
title: Home
display-title: "Leon Paternoster"
is_home: true
order: 1
---
I'm head of digital and marketing at Suffolk Libraries. I blog about working on the web, libraries and anything else that interests me. You have been warned.

<h2 class="f5 normal mt4 gray pb1 bb b--light-gray c-sans-serif">Latest blog posts</h2>

{% assign posts = site.posts | where_exp: "post", "post.note != true" %}

<ul class="list ma0 pa0 c-linky-visited">

{% include list.html post-limit=10 %}

</ul>

<hr class="pb4">

<ul class="c-linky-visited">

    <li><a href="/feed/index.xml/">RSS feed</a></li>
    <li><a rel="me" href="https://twitter.com/leonpaternoster/">Twitter</a></li>
    <li><a href="https://micro.blog/leonp/" rel="me">micro.blog</a></li>
    <li><a rel="me" href="https://github.com/leonp">Github</a></li>
    <li>leon.paternoster@zoho.com</li>

</ul>
