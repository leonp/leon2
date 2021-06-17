---
layout: default
title: Leon Paternoster
display-title: "13 years (and counting) of building websites, managing digital and marketing teams and project managing complex digital projects."
nav-title: "Home"
is_home: true
order: 1
prose-headings: true
hyphens: true
visited-links: true
underlined-links: true
hide-title: true
---

## About

I’m Leon, head of digital and marketing at Suffolk Libraries, the not-for-profit that runs Suffolk’s library service. I’ve got 13 years’ experience of digital strategy, project management and branding. [Read more about me](/about).

## Contact

<ul class="list ph0">

	<li>leon.paternoster@zoho.com</li>
	<li><a href="https://uk.linkedin.com/in/leonpaternoster/">LinkedIn</a></li>

</ul>

## Work

<div class="mt3">

{% assign projects = site.work | sort: "work-order" %}

{% for project in projects %}

	<div class="mb2 mb0-l flex-l">

		<div class="w-75-l pr2-l"><a class="db" href="{{ project.url }}">{{ project.title }}</a></div>

		<div class="w-25-l pl2-l tr-l f6">{{ project.year }}</div>

	</div>

{% endfor %}

</div>

## Writing

<div class="mt3">

{% assign posts = site.posts | where: "featured", "true" %}

{% for post in posts limit:3 %}

	<div class="mb2 mb0-l flex-l">

		<div class="w-75-l pr2-l"><a class="db" href="{{ post.url }}">{{ post.title }}</a></div>

		<div class="w-25-l pl2-l tr-l f6">{{ post.date | date: "%Y" }}</div>

	</div>

{% endfor %}

</div>

[More articles](/posts).
