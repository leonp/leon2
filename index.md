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

Digital development, strategy and project management since 2008. Head of digital and marketing at [Suffolk Libraries](https://www.suffolklibraries.co.uk).

## Work

<ul>

{% assign projects = site.work | sort: "work-order" %}

{% for project in projects %}

	<li><a href="{{ project.url }}">{{ project.title }}</a></li>

{% endfor %}

</ul>

## Qualifications

- BA (Hons) Literature and Philosophy
- PGCE (English, secondary) — Qualified Teacher Status
- [Open University Project Management short course BG007](https://www.open.ac.uk/courses/short-courses/bg007)

## Contact

- [Twitter](https://mobile.twitter.com/leonpaternoster/)
- [micro.blog](https://micro.blog/leonp/)
- [LinkedIn](https://uk.linkedin.com/in/leonpaternoster/)
- [Github](https://github.com/leonp/)
- leon.paternoster@zoho.com

