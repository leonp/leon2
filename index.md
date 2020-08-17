---
layout: default
title: Leon Paternoster
display-title: "Leon Paternoster"
nav-title: "Home"
is_home: true
order: 1
prose-headings: true
hyphens: true
visited-links: true
underlined-links: true
---

I’m Leon, head of Digital and Marketing at <a href="https://www.suffolklibraries.co.uk">Suffolk Libraries</a>, the not-for-profit that runs the library service in Suffolk. I conceived and developed <a href="https://dootrix.com/verso">Verso</a>, a lightweight, portable self-service system for Libraries.

I’ve been managing websites, projects and apps in the public and not-for-profit sectors since 2008. I’m interested in prioritising user requirements, accessibility and simple, clear and resilient design.

**[Find out more &rarr;](/about/)**

## Contact me

<ul>

<li><a href="https://mobile.twitter.com/leonpaternoster/">Twitter</a></li>
<li><a href="https://micro.blog/leonp/">micro.blog</a></li>
<li><a href="https://uk.linkedin.com/in/leonpaternoster">LinkedIn</a></li>
<li>leon.paternoster@zoho.com</li>

</ul>

## Writing

<ul class="mv3 pa0 list">

{% assign posts = site.posts | where: "featured", "true" %}

{% for post in posts %}

    <li class="lh-title"><a class="db pv2 no-underline" href="{{ post.url }}">{{ post.title }}</a></li>

{% endfor %}

</ul>
