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
in_nav: true
---

Digital strategy and project management since 2008. Head of digital and marketing at [Suffolk Libraries](https://www.suffolklibraries.co.uk).

## Qualifications

- BA (Hons) Literature and Philosophy
- PGCE (English, secondary) — Qualified Teacher Status
- [Open University Project Management short course BG007](https://www.open.ac.uk/courses/short-courses/bg007)

## Contact

- [Twitter](https://mobile.twitter.com/leonpaternoster/)
- [micro.blog](https://micro.blog/leonp/)
- [LinkedIn](https://uk.linkedin.com/in/leonpaternoster)
- leon.paternoster@zoho.com

## Writing

<ul class="mv3 pa0 list">

{% assign posts = site.posts | where: "featured", "true" %}

{% for post in posts %}

    <li class="mb3"><a href="{{ post.url }}">{{ post.title }}</a></li>

{% endfor %}

</ul>
